# Vice Details — Scroll Hero Video Prompt

**Created:** 2026-04-26
**Purpose:** Website hero background video — dirty → foam → clean transformation on scroll

---

## Image Sequence Reference

| Frame | Description | File |
|-------|-------------|------|
| 1 — DIRTY | Black BMW M3 sedan caked in thick brown mud and grime, parked on wet concrete in front of a modern dark building with large glass windows. Overcast sky, puddles on ground. | `ChatGPT Image Apr 26, 2026, 02_49_22 AM.png` |
| 2 — FOAM | Same black BMW M3 sedan now completely covered in thick white soap foam, dripping down the body panels, wheels, and windows. Same location, same angle, same lighting. | `ChatGPT Image Apr 26, 2026, 02_48_08 AM.png` |
| 3 — CLEAN | Same black BMW M3 sedan now spotless, glossy, mirror-like black paint reflecting the sky and building. Wet ground still visible. Same location, same angle, same lighting. | `ChatGPT Image Apr 26, 2026, 02_48_11 AM.png` |

---

## Video Prompt (Copy & Paste)

```
A cinematic, seamless transformation video of a black BMW M3 sedan parked on wet concrete in front of a modern dark building with large glass windows. 

The video begins with the car completely caked in thick brown mud and grime — dirty, dull, neglected. The camera is static, locked-off at a three-quarter front angle. 

Over the course of the video, thick white soap foam cascades down from the roof and hood, slowly enveloping the entire vehicle — windows, wheels, body panels — until the car is fully coated in dripping white foam. 

Then the foam dissolves and washes away in smooth vertical streaks, revealing pristine, glossy black paint underneath. The final frame shows the car spotless, mirror-shine finish, reflections sharp, looking brand new. 

The background, lighting, and camera angle remain completely identical throughout — only the car's surface state changes. Overcast natural lighting, moody and premium atmosphere. 

Slow, smooth, hypnotic transition. No camera movement. No cuts. One continuous morph. Seamless loop. 4K, photorealistic, cinematic color grading.
```

---

## Recommended Video AI Tools

| Tool | Best For | Notes |
|------|----------|-------|
| **Runway Gen-3 Alpha** | Image-to-video morphing | Upload Frame 1 (dirty) as image prompt, describe the full transition |
| **Kling AI** | Realistic motion | Strong at maintaining object consistency across frames |
| **Pika Labs** | Smooth transitions | Good for gradual morphs and dissolves |
| **Haiper** | Free tier available | Decent quality for testing |

---

## Tips for Best Results

1. **Upload Frame 1 (dirty)** as the base image in the video generator
2. **Use the full prompt above** as the text prompt
3. **Set motion strength / camera movement to ZERO** — you want a locked-off static shot
4. **Generate 5–10 seconds** — long enough to feel smooth, short enough to loop seamlessly
5. **If the tool supports keyframes:** upload Frame 1 as start, Frame 3 as end, and describe the foam stage in the prompt
6. **Generate multiple versions** and pick the one with the smoothest foam-to-clean transition
7. **Loop test:** the video should end exactly where it began (dirty) OR be cut to end on clean for a one-way scroll reveal

---

## Website Implementation Notes

- Use as a **fixed background video** behind the hero section
- Apply a **dark overlay** (rgba(0,0,0,0.4)) so white headline text pops
- **Scroll-reactive:** tie video playback position to scroll progress so the user "scrubs" through dirty → foam → clean as they scroll down
- **Fallback:** use Frame 3 (clean) as a static background image for mobile/browsers that block autoplay
- Compress to **H.264 MP4, 1080p, under 5MB** for fast web loading

---

> **Status:** Prompt ready — generate video and place the final file in `vice-details/website-assets/` when complete.
