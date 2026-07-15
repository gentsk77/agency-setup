# Component registry

Each component is a self-contained installable: a `COMPONENT.md` manifest (version, target paths, placeholders, dependencies, install notes) plus `templates/` holding the exact files the installer copies. The install procedure itself lives in `/SETUP.md`; this table is the registry it resolves against.

| Component | Version | What it installs | Requires |
|---|---|---|---|
| `memory-core` | 1.0.0 | STATE / journal / decisions / open-questions files with mutation rules | (none) |
| `claude-md-skeleton` | 1.0.0 | Budgeted CLAUDE.md: session protocol, repo map, invariants | memory-core |
| `gateway` | 1.0.0 | Product-lead agent charter + gateway skill (intake, routing, dispatch) | memory-core, claude-md-skeleton |
| `dev-lanes` | 1.0.0 | Builder charter, coding-handoff skill, parallel-lanes skill | gateway |
| `review-law` | 1.0.0 | REVIEW.md, reviewer charter, PR template, review flow | dev-lanes |
| `steward` | 1.0.0 | Recurring process-audit skill | memory-core |
| `gradable-rules` | 1.0.0 | Rule-article format, amendment log, validate script, eval pipeline skills | gateway |
| `design-lane` | 1.3.0 | Design-lead charter, conventions checklist, establishment + proposal lifecycle, starter sheet + generated design.md | gateway |
| `ci-gates` | 1.0.0 | Docs-lint GitHub Actions workflow, or local pre-commit equivalent | memory-core |

## Conventions every component follows

- **Placeholders** use `{{NAME}}` syntax; every placeholder a template uses is listed in its COMPONENT.md. The installer fills them from interview answers.
- **Provenance stamp:** the installer prepends `<!-- agency-setup: <component>@<version>, installed <YYYY-MM-DD> -->` to every installed file. The harvest pass keys off these stamps.
- **Versioning:** bump the version on any template change, via an amendment-style entry in the component's COMPONENT.md changelog. Never edit a released template silently.
- **Person-agnostic:** templates speak in roles (maintainer, builder, reviewer), never names; no domain content from any source repo.
