# Skills & Knowledge Library

## Scroll-Linked Video Animation

### 3 Methods

| Method | Best For | Pros | Cons |
|--------|---------|------|------|
| **WebCodecs + Canvas** | Chrome-only apps | Most performant | Chrome only, load delay |
| **playbackRate** | Forward-only | Extremely smooth | Cannot reverse |
| **currentTime** | Universal | Works everywhere | Needs keyframe encoding |

### Best Practice Code (GSAP + currentTime)

```tsx
const video = videoRef.current;
const container = containerRef.current;

const setup = () => {
  gsap.to(video, {
    currentTime: video.duration,
    ease: "none",
    scrollTrigger: {
      trigger: container,
      start: "top top",
      end: "bottom top",
      scrub: 1,
    },
  });
};

video.addEventListener("loadeddata", setup, { once: true });
```

### Video Encoding for Smooth Scrubbing

```bash
# Keyframe every frame = butter smooth
ffmpeg -i input.mp4 -c:v libx264 -g 1 -pix_fmt yuv420p output.mp4
```

### Key Options
- `scrub: 1` — Smooth 1-second catch-up
- `pin: true` — Keep video visible while scrolling
- `end: "+=500"` — Control scroll distance

---

## Vice Miami Color Palette

| Role | Hex | Usage |
|------|-----|-------|
| Background | `#080810` | Page bg |
| Card | `#0f0f1a` | Cards, sections |
| Border | `#1a1a30` | Borders, dividers |
| Pink | `#ff2d7a` | CTAs, primary accent |
| Pink Light | `#ff6b9d` | Hover states |
| Cyan | `#00f0ff` | Labels, prices, secondary |
| Cyan Dim | `#00b8c4` | Hover cyan |
| Text | `#f0f0f5` | Body text |
| Muted | `#8a8aa0` | Secondary text |
