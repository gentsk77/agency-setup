# Component: memory-core

- **Version:** 1.0.0
- **Requires:** nothing
- **Installs to:** `docs/` in the target repo
- **Placeholders:** `{{PROJECT_NAME}}`, `{{DATE}}`

## What it installs

| Template | Target | Mutation rule |
|---|---|---|
| `templates/STATE.md` | `docs/STATE.md` | Overwrite freely; must be current whenever work lands on the trunk |
| `templates/journal.md` | `docs/journal.md` | Append-only, reverse-chronological |
| `templates/decisions.md` | `docs/decisions.md` | Append-only; supersede via a new D-number plus a status stamp on the old entry |
| `templates/open-questions.md` | `docs/open-questions.md` | Check off with a pointer to where it was resolved; add freely |

## Install notes

- This is the foundation component; every profile includes it. It mechanizes P01 (repo is memory), P02 (one fact, one home), and P08 (append-only law).
- After installing, write the first STATE.md by hand (the installer generates it from interview answers): what the project is, what happens next, what is blocked.
- The decision log starts empty except for its header. Do not backfill imagined history; the first D-number is the first real ruling.

## Changelog

- 1.0.0 (2026-07-14): initial release.
