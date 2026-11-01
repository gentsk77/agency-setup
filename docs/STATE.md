# STATE: agency-setup

One-screen handoff note. Overwrite freely; keep current.

## Orientation

State as of 2026-11-01. The library has doctrine P01 to P10, nine registered components (design-lane at 1.5.0; the rest at 1.0.0), four profiles, the SETUP.md router, the harvest procedure (`setup/harvest.md`), and `setup/sources.md` (the inbound flow for external material, and the default-library menu that design-lane's establishment step reads). Decisions run D1 to D8. Design and build plan: `docs/specs/` and `docs/plans/`.

PR #1 (taste harvest, source intake, PR-only trunk, design-lane 1.5.0) merged 2026-07-20. The library has been installed into three private repos of the maintainer via SETUP.md; each carries a `docs/setup-manifest.md` naming this library as its source. The design-lane 1.4.0 changes reached the library by harvesting one install's design rounds; installs pick up library changes only at their next SETUP.md upgrade pass.

The brownfield adoption proposal (`setup/proposals/2026-08-11-brownfield-adoption.md`) is merged as a proposal. Its status is still "proposed, unratified": nothing in SETUP.md or the components implements it yet.

**Trunk is PR-only (D7):** `main` takes no direct commits; every change goes through a reviewed PR. Enforced by a tracked client-side hook (`scripts/hooks/`; enable per clone with `git config core.hooksPath scripts/hooks`). Server-side branch protection would be stronger; see the first next action.

## Now

No change is in flight on the library itself. The open work is the pending proposal (brownfield adoption, awaiting a ratify-or-reject ruling and then implementation) and the known template gaps listed under Next actions.

## Next actions

- Maintainer: decide server-side enforcement of D7. Until branch protection or a ruleset is enabled, the hook is the only guard and is bypassable with `--no-verify`. Record the outcome as a new decision with a status stamp on D7.
- Maintainer: rule on the brownfield adoption proposal (ratify, amend, or reject). If ratified, implement it as a SETUP.md change plus component version bumps.
- Fix known template gaps found while reading installs: SETUP.md Step 3.5 stamps the first line, which breaks files that start with a shebang and generated files that a check script compares; `generate_design_md.py` ignores `{{DESIGN_SYSTEM_PATH}}`; the ci-gates local hook installs to untracked `.git/hooks`. Route each as a component version bump.
- Run a harvest pass over the installs that have accumulated local adaptations of library templates, and land the result as versioned bumps.
- When a second source gets flagged, run `setup/sources.md` and confirm the procedure holds beyond the first entry.

## Blocked / waiting

- Nothing is blocked. Items above wait on maintainer rulings.
