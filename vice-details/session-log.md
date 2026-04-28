# Vice Details — Session Log

**Project:** Vice Details Website + Growth Systems
**Started:** 2026-04-26
**Platform:** MacBook (Kimi Code CLI)
**Saved By:** Kimi

---

## Session 1 — Project Kickoff & Website Planning

### What We Did
1. Established filing system for all Vice Details information
2. Saved complete master business context for Vice Details
3. Began planning the Vice Details website
4. Created scroll-hero video prompt for website background

---

## Website Direction Decided

**Concept:** Premium mobile detailing website with a **scroll-reactive transformation video** as the hero background.

**Visual Hook:** As the user scrolls down, they watch a car transform from:
- DIRTY (mud-covered) → FOAM (soap-covered) → CLEAN (spotless, shiny)

This creates an immediate, visceral "before/after" experience that sells the detailing service without reading a word.

---

## Image Assets — Scroll Hero Video

Three photos provided by user for video generation. All same car, same location, same angle:

| Stage | Description | File Location on Mac |
|-------|-------------|---------------------|
| **Frame 1 — DIRTY** | Black BMW M3 sedan caked in thick brown mud and grime, parked on wet concrete in front of modern dark building. Overcast sky, puddles. | `/Users/alofx/Downloads/ChatGPT Image Apr 26, 2026, 02_49_22 AM.png` |
| **Frame 2 — FOAM** | Same BMW M3 completely covered in thick white soap foam, dripping down body panels, wheels, windows. Same location/angle/lighting. | `/Users/alofx/Downloads/ChatGPT Image Apr 26, 2026, 02_48_08 AM.png` |
| **Frame 3 — CLEAN** | Same BMW M3 spotless, glossy mirror-like black paint reflecting sky and building. Wet ground visible. Same location/angle/lighting. | `/Users/alofx/Downloads/ChatGPT Image Apr 26, 2026, 02_48_11 AM.png` |

**Video Generation Decision:** Upload ONLY Frame 1 (dirty) as the base image + use the detailed text prompt. Generate 3–5 versions and pick the best one. Most AI video tools (Runway, Kling, Pika, Haiper) work with one starting image + text prompt.

**Full video prompt saved in:** `website-assets/scroll-hero-video-prompt.md`

---

## Tech Stack (Proposed — Not Yet Built)

Based on the user's existing projects (Alo Scaling Solutions, ATE), the Vice Details website will likely use:

- **Next.js 16** (App Router, static export)
- **TypeScript**
- **Tailwind CSS**
- **GSAP + ScrollTrigger** (for scroll-reactive video scrubbing)
- **Lenis** (smooth scroll)

**Hero Implementation Plan:**
- Fixed background video behind hero section
- Scroll progress tied to video currentTime (scrubbing effect)
- Dark overlay (rgba(0,0,0,0.4)) for text readability
- Fallback static image (Frame 3 — clean) for mobile/autoplay-blocked browsers
- Video compressed to H.264 MP4, 1080p, under 5MB

---

## Next Steps / To-Do

1. **Generate scroll hero video** using the provided prompt + Frame 1 image
2. **Build Vice Details website framework** (Next.js project setup)
3. **Implement scroll-reactive hero** with GSAP ScrollTrigger video scrub
4. **Add remaining sections:** Services/Pricing, How It Works, Before/After Gallery, Testimonials, Booking CTA, Contact/Footer
5. **Integrate booking system** (per master context requirements)
6. **Set up review generation workflow**
7. **Deploy website**

---

## Files Created in This Session

| File | Location | Purpose |
|------|----------|---------|
| `vice-master-context.md` | `-project-notes/vice-details/` | Complete business context, pricing, systems, operations |
| `scroll-hero-video-prompt.md` | `-project-notes/vice-details/website-assets/` | AI video generation prompt + tool recommendations |
| `session-log.md` | `-project-notes/vice-details/` | This file — session history and decisions |

---

## Notes for Future Sessions

- Vice Details is the highest priority project right now
- Revenue-focused decisions only — no fluff
- Website must drive bookings, not just look good
- All systems (booking, payment, reviews, rebooking) need to integrate eventually
- Keep design premium, dark, moody — matches the dirty→clean transformation concept

---

> **Status:** Website planning phase complete. Awaiting video asset generation to begin build.

---

## Session 2 — Website Build Complete

### What We Did
1. Installed Node.js and ffmpeg on MacBook
2. Combined 3 videos into one scroll-reactive hero video (4K + 1080p web version)
3. Created Vice Details website at `~/projects/vice-details`
4. Built full Next.js site with scroll-reactive hero, services, how it works, booking CTA, footer
5. Pushed code to GitHub: `github.com/alofx/vice-details`

### Files Created
- `~/projects/vice-details/` — Full Next.js project
- `hero-scroll-video-4k.mp4` — 4K version in vice-details assets + ALO SCALE folder
- `hero-scroll.mp4` — Web-optimized 1080p version in project public folder

### Website Sections
| Section | Component |
|---------|-----------|
| Navbar | `components/Navbar.tsx` |
| Scroll Hero | `components/ScrollHero.tsx` |
| Services | `components/Services.tsx` |
| How It Works | `components/HowItWorks.tsx` |
| Booking CTA | `components/CTA.tsx` |
| Footer | `components/Footer.tsx` |

### To Pull on PC
```bash
cd C:\Users\babyg\projects  # or wherever
git clone https://github.com/alofx/vice-details.git
cd vice-details
npm install
npm run dev
```

---

> **Status:** Website v1 complete and live on GitHub. Preview at `http://localhost:3000`
