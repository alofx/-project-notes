# Agent Memory: Website Projects

## GitHub Repositories (Source of Truth)
Both projects are synced to GitHub for cross-device access.

| Project | GitHub Repo | Local Windows | Local Mac |
|---------|-------------|---------------|-----------|
| **Alo Scaling Solutions** | [github.com/alofx/alo-scaling-solutions](https://github.com/alofx/alo-scaling-solutions) | `C:\Users\babyg\alo-scaling-solutions\` | `~/projects/alo-scaling-solutions/` |
| **ATE — All The Essentials** | [github.com/alofx/ate](https://github.com/alofx/ate) | `C:\Users\babyg\ate\` | `~/projects/ate/` |

**GitHub Account:** `alofx` | **Email:** alofxhayati@gmail.com

---

## MacBook Setup Instructions (for Kimi/Claude)
When opening this project on a Mac for the first time:

```bash
# 1. Install Kimi CLI (if not already)
curl -fsSL https://kimi.com/install.sh | bash

# 2. Clone repos
mkdir -p ~/projects
cd ~/projects
git clone https://github.com/alofx/alo-scaling-solutions.git
git clone https://github.com/alofx/ate.git

# 3. Run Alo
cd ~/projects/alo-scaling-solutions
npm install
npm run dev
# Open http://localhost:3000

# 4. Run ATE (in a new terminal)
cd ~/projects/ate
npm install
npm run dev
# Open http://localhost:3000 (or 3001 if Alo is running)
```

---

## Cross-Device Sync Workflow
Whenever changes are made on one computer:

```bash
# On the computer where changes were made:
git add .
git commit -m "describe what changed"
git push

# On the other computer:
git pull
```

**Always commit and push before switching devices.**

---

## Project 1: Alo Scaling Solutions (COMPLETE)
Premium growth agency website with scroll animations.
- **Status:** Complete with premium upgrade
- **Tech:** Next.js 16, GSAP, Lenis, Tailwind
- **Live:** `http://localhost:3000`

---

## Project 2: ATE — All The Essentials (COMPLETE DEMO)
B2B supply & distribution platform with public website + operations dashboard.
- **Status:** Demo complete — ready to preview
- **Tech:** Next.js 16, Tailwind, TypeScript

### ATE Public Website (Dark Theme)
| Page | Route | Features |
|------|-------|----------|
| Home | `/` | Hero, trust stats, industries grid, product showcase, CTA |
| About | `/about` | Company story, benefits grid |
| Products | `/products` | Category cards, product catalog (no prices), request quote CTAs |
| Industries | `/industries` | 12 industry cards with descriptions |
| Contact | `/contact` | Quote request form, contact info |

### ATE Operations Dashboard (Light Theme)
| Page | Route | Features |
|------|-------|----------|
| Login | `/dashboard/login` | Branded sign-in screen |
| Dashboard | `/dashboard` | 6 stat cards, pending quotes, recent orders, low stock alerts |
| Inventory | `/dashboard/inventory` | Full product table with stock levels, thresholds, suppliers |
| Customers | `/dashboard/customers` | Customer accounts with tiers, orders, balances |
| Quotes | `/dashboard/quotes` | Quote list with status badges (Pending, Approved, Expired) |
| Orders | `/dashboard/orders` | Order tracking with fulfillment statuses |
| Payments | `/dashboard/payments` | Outstanding balances, payment methods, send invoice actions |

### ATE Design
- Public: Dark navy (#0a0a0f) + gold accent (#d4a853)
- Dashboard: Light slate (#f8f9fb) + same gold accent
- Brand: "ATE." text logo with gold square mark

### How to Run ATE
```bash
# Windows:
cd C:\Users\babyg\ate
npm install
npm run dev

# Mac:
cd ~/projects/ate
npm install
npm run dev
```
- Public site: `http://localhost:3000`
- Dashboard: `http://localhost:3000/dashboard`
- Dashboard login: `http://localhost:3000/dashboard/login`

---

## Session Log
| Date | What We Did |
|------|-------------|
| 2026-04-23 | Created Alo Scaling Solutions website |
| 2026-04-24 | Premium upgrade for Alo (cursor glow, 3D tilt, living dashboard, etc.) |
| 2026-04-24 | Built ATE — All The Essentials complete B2B supply platform demo |
| 2026-04-24 | Set up GitHub repos for both projects; added .gitignore; committed all code |

---

> **Note**: Read `C:\Users\babyg\Claude+Kim\alo-business-context.md` for Alo business details.
> **Note**: Read `C:\Users\babyg\Claude+Kim\handoff_for_kimi.md` for detailed Alo technical notes.
> **Note**: Read `C:\Users\babyg\ate\PROJECT_NOTES.md` for detailed ATE technical notes.
