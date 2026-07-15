# Component: ci-gates

- **Version:** 1.0.0
- **Requires:** memory-core
- **Installs to:** `.github/workflows/docs-lint.yml` (GitHub flavor) or `.git/hooks/pre-commit` (local flavor)
- **Placeholders:** `{{WORD_BUDGET}}` (must match the number in CLAUDE.md's maintenance section)

## What it installs

The mechanized gates (P07) for the memory core and instruction layer. Both flavors run the same three checks:

1. **Word budget:** `CLAUDE.md` word count within `{{WORD_BUDGET}}`.
2. **STATE phrasing:** `docs/STATE.md` contains no merge-falsified phrasing (`awaiting merge`, `unpushed`, `not yet merged`).
3. **PR title grammar** (GitHub flavor only): `type: summary` with type in `feat | fix | docs | design | wave`.

| Template | Target | When |
|---|---|---|
| `templates/github/workflows/docs-lint.yml` | `.github/workflows/docs-lint.yml` | Repo has a GitHub remote |
| `templates/hooks/pre-commit` | `.git/hooks/pre-commit` (mark executable) | Local-only repo |

## Install notes

- Install exactly one flavor at setup; a repo that later gains a remote adds the workflow and can keep the hook.
- The local hook must never be the only copy of a rule's rationale; it enforces, CLAUDE.md points, decisions explain (one fact, one home).
- If gradable-rules is installed, add `python scripts/validate_rules.py` as a fourth check in whichever flavor was chosen.

## Changelog

- 1.0.0 (2026-07-14): initial release.
