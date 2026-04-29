# Scroll-Linked Video Animation — Research & Techniques

**Date:** 2026-04-28
**Purpose:** How to attach a video to the mouse scroll wheel for scrub animations

---

## The Goal

Make a video scrub forward/backward exactly in sync with the user's scroll wheel, so scrolling down = video plays forward, scrolling up = video reverses.

---

## 3 Methods (Ranked by Performance)

### Method 1: WebCodecs API + Canvas (Best, Chrome Only)
- Decodes every video frame ahead of time into a canvas
- Most performant, smoothest playback
- **Cons:** Only works in Chrome, takes time to decode on load
- **Use when:** You control the browser environment (kiosk, Chrome-only app)

### Method 2: HTML5 Video + playbackRate (Smooth, No Reverse)
- Video plays normally, but playback speed is tied to scroll velocity
- Extremely smooth in forward direction
- **Cons:** Cannot play backwards (playbackRate can't be negative)
- **Use when:** One-direction scroll only

### Method 3: HTML5 Video + currentTime (Universal, What We Use)
- Directly set `video.currentTime` based on scroll progress
- Works in ALL browsers, forward AND reverse
- **Cons:** Can be choppy if video isn't encoded with keyframes every frame
- **Use when:** General web, need bidirectional scroll (our case)

> **For Method 3, encode videos with `-g 1` (keyframe every frame) for silky smooth seeking.**

---

## GSAP ScrollTrigger Video Scrub — Best Practice Code

```tsx
"use client";
import { useEffect, useRef } from "react";
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

export default function ScrollVideo() {
  const containerRef = useRef<HTMLDivElement>(null);
  const videoRef = useRef<HTMLVideoElement>(null);

  useEffect(() => {
    const video = videoRef.current;
    const container = containerRef.current;
    if (!video || !container) return;

    // IMPORTANT: Wait for video metadata before setting up scroll
    const setup = () => {
      const duration = video.duration || 1;
      
      gsap.to(video, {
        currentTime: duration,
        ease: "none",
        scrollTrigger: {
          trigger: container,
          start: "top top",
          end: "bottom top",
          scrub: 1, // Smooth catch-up (1 second lag)
          pin: false, // Set true if you want the section to stick
        },
      });
    };

    // Wait for video to be ready
    if (video.readyState >= 2) {
      setup();
    } else {
      video.addEventListener("loadeddata", setup, { once: true });
    }

    return () => {
      ScrollTrigger.getAll().forEach((t) => t.kill());
    };
  }, []);

  return (
    <div ref={containerRef} className="h-[200vh]">
      <div className="sticky top-0 h-screen">
        <video
          ref={videoRef}
          src="/videos/video.mp4"
          muted
          playsInline
          preload="auto"
          className="h-full w-full object-cover"
        />
      </div>
    </div>
  );
}
```

---

## Key GSAP ScrollTrigger Options

| Option | What It Does | For Video Scrub |
|--------|-------------|-----------------|
| `scrub: true` | Animation progress = exact scroll position | Jerky, immediate |
| `scrub: 1` | Animation catches up over 1 second | **Smooth, recommended** |
| `scrub: 0.5` | Faster catch-up | More responsive |
| `pin: true` | Element sticks while scrolling | Keep video visible longer |
| `end: "+=500"` | Scroll 500px to complete animation | Controls scroll distance |
| `end: "bottom top"` | End when element bottom hits viewport top | Natural scroll flow |

---

## Video Encoding for Smooth Scrubbing

### FFmpeg command (Keyframe every frame = smoothest)
```bash
ffmpeg -i input.mp4 -c:v libx264 -preset fast -crf 23 -g 1 -pix_fmt yuv420p output.mp4
```
- `-g 1` = keyframe every frame (critical for smooth seeking)
- `-crf 23` = quality level
- File size will be larger but scrubbing is buttery smooth

### Web-optimized version (smaller file, still smooth enough)
```bash
ffmpeg -i input.mp4 -c:v libx264 -preset fast -crf 28 -pix_fmt yuv420p output.mp4
```
- Default keyframe interval (~250 frames)
- Smaller file, slightly less smooth but usually fine

---

## External Library: scrolly-video

GitHub: `github.com/dkaoster/scrolly-video`

A React component that automatically handles all 3 methods with fallback:
1. Tries WebCodecs first
2. Falls back to playbackRate
3. Falls back to currentTime

```bash
npm install scrolly-video
```

```tsx
import ScrollyVideo from "scrolly-video/dist/ScrollyVideo.cjs.js";

<ScrollyVideo
  src="/videos/video.mp4"
  transitionSpeed={1}
  frameThreshold={0.1}
/>
```

---

## Performance Tips

1. **Compress video** — Under 5MB for web, under 10MB max
2. **Use 1080p max** — 4K is overkill and hurts performance
3. **Mute the video** — Autoplay requires muted attribute
4. **preload="auto"** — Load video eagerly for instant scrubbing
5. **Use `requestAnimationFrame`** — Never update currentTime in a raw scroll listener
6. **Kill ScrollTriggers on unmount** — Prevents memory leaks

---

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Video snaps back to start after scrolling past | Add `onLeaveBack` to reset, or use `toggleActions` |
| Choppy/scrubby video playback | Encode with `-g 1` (keyframes every frame) |
| Video doesn't start at frame 1 | Wait for `loadeddata` event before creating ScrollTrigger |
| Mobile Safari issues | Use `playsInline` attribute, test on real device |
| ScrollTrigger not working in React | Use `"use client"` directive, register plugin in useEffect |

---

## Resources

- [GSAP ScrollTrigger Docs](https://gsap.com/docs/v3/Plugins/ScrollTrigger/)
- [GSAP Video Scrub Forum Thread](https://gsap.com/community/forums/topic/32782-video-scroll-animation/)
- [scrolly-video Library](https://github.com/dkaoster/scrolly-video)
- [Apple AirPods Pro Scroll Effect (CodePen)](https://codepen.io/GreenSock/pen/9e810322d70c306de2d18237d0cb2d78)

---

> **Current Implementation:** We use Method 3 (currentTime) with GSAP ScrollTrigger scrub: 1. The video was encoded at 24fps with standard keyframe intervals. For even smoother scrubbing, re-encode with `-g 1`.
