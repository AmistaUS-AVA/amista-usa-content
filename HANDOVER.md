# HANDOVER — amista-usa-content

_Last updated: 2026-09-29_

## Purpose / business context
Content (copy + images) for the **AMISTA USA** public website https://www.amistausa.com. This repo is consumed as the
`content/` git submodule of [`amista-usa-website`](https://github.com/AmistaUS-AVA/amista-usa-website). Editors change
Markdown here (often directly in the GitHub web UI); the website rebuilds automatically.

## Tech stack
Plain Markdown files with YAML front matter describing a list of **blocks** (hero, features, section, split, team, cta,
contact, accordion, image, spacer, solutionsList, industriesList, erpOptions…). Block schemas are defined in the website
repo (`src/content.config.ts`, `src/components/blocks/`). No build tooling here.

## Repository layout
| Path | What |
|---|---|
| `pages/` | Top-level pages: `home`, `about`, `contact`, `who-we-are`, `solutions`, `industries` |
| `pages/_example.md` | Reference of every block type and its options (not published — leading underscore) |
| `solutions/` | One file per solution (SAP Business One, Beas Manufacturing, ProcessForce, Produmex WMS, WiSys WMS); `order` field sorts the list |
| `industries/` | Food processing, manufacturing, pharmaceuticals, wholesale distribution |
| `uploads/` | Images referenced as `/uploads/<file>` (team photos, hero images, logos) |
| `.github/workflows/trigger-website.yml` | Sends `repository_dispatch` `content-updated` to the website repo |

## Setup & running locally
Nothing to run here. To preview, work in the website repo: `git submodule update --remote content`, then `npm run dev`.

## Configuration
- GitHub Actions secret: `WEBSITE_REPO_TOKEN` (PAT allowed to dispatch to `AmistaUS-AVA/amista-usa-website`).

## Deployment
Push to `master` → `Trigger Website Rebuild` workflow → website repo `update-content.yml` bumps the submodule and pushes
→ website `deploy.yml` builds and deploys to Cloudflare Pages (project `amista-usa-website`).
Commits containing `[skip ci]` do not trigger the rebuild (used for the HANDOVER commit).

## Current status & open items
- Latest content commit `1d58810` (Who We Are page updates, 2025-12-11) is **not live**: the website's submodule pointer
  was rolled back to `c27daea` by website commit `1985186` (2026-03-15). Re-bump the submodule in the website repo (or push a
  new content commit without `[skip ci]`) to publish it.
- An uncommitted edit to `pages/_example.md` exists only in the website's local `content/` submodule checkout
  (`D:/_projects/amista-usa-website/content`), not in this clone.

## Known gotchas
- Image paths must be `/uploads/...` (a past commit fixed a broken image path on who-we-are).
- Front matter must match the website's Zod block schemas or the website build fails.
- Files starting with `_` are ignored by routing but still parsed.

## Related projects
- [`amista-usa-website`](https://github.com/AmistaUS-AVA/amista-usa-website) (`D:/_projects/amista-usa-website`).
