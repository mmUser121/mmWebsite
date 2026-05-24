# MatterMind website repo

Single-page marketing site for MatterMind. Hosted on GitHub Pages at https://mattermind.ai.

## How it deploys

`.github/workflows/static.yml` deploys whichever folder it points at (currently `staging-0205/`) to GitHub Pages, triggered by pushes to the `live` branch. Day-to-day work lands on `main`; promotion to production is a PR from `main` → `live`.

## Folders

| Folder | Purpose |
|---|---|
| `staging-0205/` | **V1.0 — frozen.** Production source served by the Pages workflow. Git tag `V1.0` captures the shipped state. |
| `staging-v2/` | **V2 — active dev.** All new work happens here. Seeded as a copy of `staging-0205/` at V1.0. |
| `.github/workflows/` | GitHub Actions workflow that builds + deploys Pages. |

## Cutting V2 over to production

When V2 is ready to replace V1:

1. Change `path: './staging-0205'` → `path: './staging-v2'` in `.github/workflows/static.yml`
2. PR `main` → `live`
3. Merge — the workflow redeploys from `staging-v2/`

## Project docs

Detailed context (brief, design system, brand visual guide, full implementation hand-off) lives in `MMWebsiteGitHub/*.md`, one level above this repo on Steve's machine. Read `PROJECT_KNOWLEDGE.md` first when picking up the project cold.
