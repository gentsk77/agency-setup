# CLAUDE.md: agency-setup

A person-agnostic process library: doctrine (why), components (installables), SETUP.md (the router foreign agents follow), profiles (presets), harvest (the reverse flow). This repo self-hosts its own doctrine; the repo, not conversation history, is its memory.

## Session start

1. Read `docs/STATE.md` (one screen: orientation, next actions, blockers).
2. Read further only as the task demands: `docs/decisions.md` index before proposing anything structural; `components/README.md` before touching any component; `doctrine/README.md` before touching doctrine.

## Repo map

| Path | Role | Mutation rule |
|---|---|---|
| `doctrine/` | Process principles P01... | Amendment only, logged in `doctrine/amendments.md`; never edit an adopted body |
| `components/` | Versioned installables | Any template change bumps the version with a changelog entry; never silent edits |
| `SETUP.md`, `profiles/`, `setup/harvest.md`, `setup/sources.md` | Router, presets, reverse flow (from live repos), inbound flow (external sources) | Keep consistent with the registry; SETUP.md may only reference files that exist |
| `docs/STATE.md` | Handoff note | Overwrite freely, keep current |
| `docs/journal.md` | Session log | Append-only |
| `docs/decisions.md` | Rulings D1, D2, ... | Append-only; supersede via new D plus status stamp |
| `docs/open-questions.md` | Question queue | Check off with a pointer |

## Invariants

- **Person-agnostic:** roles only; no maintainer names, product names, or domain content from source repos. Mechanics cross in, domains stay out.
- **Registry consistency:** `components/README.md` versions match every COMPONENT.md; profiles name only registered components.
- **No em dashes** in any artifact.
- **Git:** no commit or push without in-the-moment maintainer approval. Changes to `main` go through a reviewed PR, never a direct commit (a client-side hook enforces this: `git config core.hooksPath scripts/hooks`; D7).
- **Maintainer gates:** doctrine amendments and component version bumps need explicit maintainer sign-off; harvest proposes, never applies unratified.

## Session end

When a session materially changes thinking, files, or direction: refresh `docs/STATE.md`, append a `docs/journal.md` entry, route durables to their homes, then stop and wait for commit approval.

## Maintaining this file

Budget 400 words. A rule earns entry only after the same mistake happens twice; rationale lives in `docs/decisions.md`. Prune by the deletion test. Prefer a mechanized gate over new prose.
