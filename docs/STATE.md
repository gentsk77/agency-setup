# STATE: agency-setup

One-screen handoff note. Overwrite freely; keep current.

## Orientation

The library is built as of 2026-07-14, with a taste harvest and a components-by-default posture landed 2026-07-18: doctrine P01 to P10, nine registered components (design-lane now at 1.5.0; the rest at 1.0.0), four profiles, the SETUP.md router, the harvest procedure, and now `setup/sources.md` (the inbound flow for external material, and the default-library menu establishment reads). Decisions run D1 to D8. Design and build plan: `docs/specs/` and `docs/plans/`. One live install exists (a case-study repo installed from these components on 2026-07-14; its manifest names this library as source and pins design-lane at 1.3.0). The 1.4.0 changes reached the library by harvesting that install's design rounds; it picks them up only at its next SETUP.md upgrade pass.

**Trunk is now PR-only (D7):** `main` takes no direct commits; every change goes through a reviewed PR. Enforced by a tracked client-side hook (`scripts/hooks/`; enable per clone with `git config core.hooksPath scripts/hooks`). Server-side branch protection is stronger but gated by the free/private plan (see the open call below). Work on branches, open a PR, let the maintainer merge.

## Now

The taste harvest, source-intake procedure, PR-only governance, and the design-lane 1.5.0 components-by-default posture (D8) are on branch `feat/taste-harvest-source-intake` as PR #1, consolidated into clean commits at the maintainer's ask. Self-verified: var-gate proven on an injected bug, design.md `--check` green, hooks proven to block main and allow branches. No target repo has been installed from the library via SETUP.md yet.

## Next actions

- Maintainer: review and merge the open PR; then `git switch main && git pull` to sync local main.
- Maintainer: decide server-side enforcement of D7. The free/private plan blocks GitHub branch protection and rulesets; options are (a) keep the client-side hook only, (b) make the repo public (no secrets in it; a public library), (c) upgrade to Pro. Until then the hook is the only guard and is bypassable with `--no-verify`.
- Shake down SETUP.md against a real new repo; expect the first pass to surface template gaps. Route fixes as component version bumps.
- Watch the live install for the next design round; harvest again if it accumulates more universal taste rulings.
- When a second source gets flagged, run `setup/sources.md` and confirm the procedure holds beyond the first entry.

## Blocked / waiting

- The PR awaits maintainer review. Nothing else blocked.
