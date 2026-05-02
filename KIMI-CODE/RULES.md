# Filing Rules

## Storage Strategy

| Type | Storage | Why |
|------|---------|-----|
| **AI text / docs / code** | GitHub | Version history, sync, markdown |
| **Videos / images / PDFs** | Google Drive | File size, easy sharing |
| **Code projects** | GitHub repos | Built for code, branches, deploy |

## Auto-Filing System

When information is given, automatically sort into:

| Topic | Location |
|-------|----------|
| **Alo Scaling Solutions** | `alo-scaling-solutions/` folder |
| **ATE — All The Essentials** | `ate/` folder |
| **Vice Details** | `vice-details/` folder |
| **New project** | Create new folder for that project |
| **General / AI skills** | `KIMI-CODE/` folder |
| **Miscellaneous** | `miscellaneous/` folder |

## Commit Rule

After every significant session:
```bash
git add .
git commit -m "describe what we did"
git push
```

## Naming Conventions

- Use lowercase with hyphens: `session-log.md`, `vice-master-context.md`
- Date format: `YYYY-MM-DD` in session logs
- Status tags: `[ACTIVE]`, `[COMPLETE]`, `[ON-HOLD]`
