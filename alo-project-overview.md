# Alo Scaling Solutions — Website Project

## What we built
A full professional agency website rebuilt from scratch in **Next.js + GSAP + Lenis**.
Replaced the old Lovable.dev vibe-coded site with a proper SSR site for SEO and performance.

## GitHub Repository
[github.com/alofx/alo-scaling-solutions](https://github.com/alofx/alo-scaling-solutions)

## Location on computer
| Platform | Path |
|----------|------|
| Windows | `C:\Users\babyg\alo-scaling-solutions\` |
| Mac | `~/projects/alo-scaling-solutions/` |

## Tech stack
- **Next.js** — React framework with server-side rendering (best for Google SEO)
- **GSAP + ScrollTrigger** — scroll animations
- **Lenis** — smooth scroll engine
- **Tailwind CSS** — styling
- **TypeScript** — language

## Design
- Dark background: `#0a0a0a`
- Accent color: `#00ff88` (electric green)
- Fonts: Syne (headings) + Inter (body)
- Custom green cursor on desktop
- Grain texture overlay

## Site sections (in order)
1. Navbar — sticky, blur on scroll
2. Hero — animated word-by-word headline reveal
3. Marquee bar — scrolling ticker
4. Pain Points (`PainPoints.tsx`) — problem section
5. How It Works (`HowItWorks.tsx`) — pinned horizontal scroll cards
6. Stats Counter (`StatsCounter.tsx`) — numbers count up on scroll
7. Testimonials — glassmorphism cards
8. CTA (`CTA.tsx`) — booking section
9. Footer — social links, services, company links

## Important files
| File | Purpose |
|------|---------|
| `app/page.tsx` | Main page — imports all sections |
| `app/layout.tsx` | SEO metadata + Google Fonts + JSON-LD |
| `app/globals.css` | Global styles, dark theme, animations |
| `hooks/useLenis.ts` | Smooth scroll setup |
| `components/CustomCursor.tsx` | Green cursor (desktop only) |

## To-do before going live
- [ ] Replace Calendly link in `CTA.tsx` with real booking URL
- [ ] Add real social media links in `Footer.tsx`
- [ ] Deploy to Vercel (free) and point aloscalingsolutions.com domain to it

## How to run locally

### Windows
```bash
cd C:\Users\babyg\alo-scaling-solutions
npm run dev
```

### Mac
```bash
cd ~/projects/alo-scaling-solutions
npm install
npm run dev
```
Then open http://localhost:3000

## How to deploy
1. Push folder to GitHub (done)
2. Go to vercel.com → New Project → import repo → Deploy
3. Point aloscalingsolutions.com DNS to Vercel

## Cross-Device Sync
This project is tracked on GitHub. To sync changes between computers:

```bash
# After making changes:
git add .
git commit -m "describe changes"
git push

# On the other computer:
git pull
```

## Status (as of 2026-04-24)
- Code: COMPLETE
- Node.js: Installed
- npm install: Done
- GitHub: Synced
- Live URL: Not deployed yet
