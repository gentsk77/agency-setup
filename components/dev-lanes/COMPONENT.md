# Component: dev-lanes

- **Version:** 1.0.0
- **Requires:** gateway
- **Installs to:** `.claude/agents/builder.md`, `.claude/skills/coding-handoff/SKILL.md`, `.claude/skills/parallel-lanes/SKILL.md`
- **Placeholders:** `{{TEST_COMMAND}}`, `{{TYPECHECK_COMMAND}}`

## What it installs

The execution machinery for real development: written handoffs with acceptance criteria, branch-per-work-item with per-commit gates, squash-merge discipline, and (when running 2+ concurrent workstreams) the draft-PR lane registry with shared-file region ownership.

| Template | Target |
|---|---|
| `templates/agents/builder.md` | `.claude/agents/builder.md` |
| `templates/skills/coding-handoff/SKILL.md` | `.claude/skills/coding-handoff/SKILL.md` |
| `templates/skills/parallel-lanes/SKILL.md` | `.claude/skills/parallel-lanes/SKILL.md` |

## Placeholder guidance

- `{{TEST_COMMAND}}` / `{{TYPECHECK_COMMAND}}`: the project's actual gate commands (e.g. `npm test`, `tsc --noEmit`, `pytest`, `cargo check`). If the project has no tests yet, set the placeholder to the honest current gate and record an open question to raise it.

## Install notes

- Assumes a GitHub-style PR flow. For local-only repos, keep the branch and handoff discipline; the "draft PR registry" degrades to a `git branch` listing and the review gate becomes a maintainer read of the branch diff.
- parallel-lanes is dormant until the repo actually runs 2+ concurrent lanes; installing it early costs nothing.

## Changelog

- 1.0.0 (2026-07-14): initial release.
