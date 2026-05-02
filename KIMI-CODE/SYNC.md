# Cross-Device Sync Instructions

## GitHub Repositories

| Repo | Purpose | URL |
|------|---------|-----|
| `-project-notes` | All docs, context, session logs | github.com/alofx/-project-notes |
| `alo-scaling-solutions` | Alo agency website code | github.com/alofx/alo-scaling-solutions |
| `ate` | ATE B2B platform code | github.com/alofx/ate |
| `vice-details` | Vice Details website code | github.com/alofx/vice-details |

## Mac → Push

```bash
cd ~/Desktop/Kimi\ Documents/-project-notes
git add .
git commit -m "describe what changed"
git push

cd ~/projects/vice-details
git add .
git commit -m "describe changes"
git push
```

## PC → Pull

```bash
cd C:\Users\babyg\project-notes
git pull

cd C:\Users\babyg\alo-scaling-solutions
git pull

cd C:\Users\babyg\ate
git pull

cd C:\Users\babyg\vice-details
git pull
```

## First-Time Clone on PC

```bash
cd C:\Users\babyg
git clone https://github.com/alofx/-project-notes.git
git clone https://github.com/alofx/alo-scaling-solutions.git
git clone https://github.com/alofx/ate.git
git clone https://github.com/alofx/vice-details.git
```

## Google Drive (Videos Only)

- Store large videos, raw assets, exports
- Do NOT store code or text docs in Drive
- Use Drive for: video files, images, PDFs, presentations
