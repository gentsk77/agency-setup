# Component: gradable-rules

- **Version:** 1.0.0
- **Requires:** gateway
- **Installs to:** `rules/`, `scripts/validate_rules.py`, `.claude/skills/eval-*`
- **Placeholders:** `{{PROJECT_NAME}}`, `{{SUBJECT}}` (what gets evaluated: an idea, a vendor, a paper, a candidate design)

## What it installs

The "gradable law" pattern: rules that carry their own rubric (Statement / Grading / Evidence required), changed only by logged amendment, plus a pipeline that runs candidates through intake grilling, research, and isolated grading with a bounded revision loop.

| Template | Target |
|---|---|
| `templates/rules/README.md` | `rules/README.md` |
| `templates/rules/article-template.md` | `rules/article-template.md` |
| `templates/rules/amendments.md` | `rules/amendments.md` |
| `templates/scripts/validate_rules.py` | `scripts/validate_rules.py` |
| `templates/skills/eval-run/SKILL.md` | `.claude/skills/eval-run/SKILL.md` |
| `templates/skills/eval-intake/SKILL.md` | `.claude/skills/eval-intake/SKILL.md` |
| `templates/skills/eval-research/SKILL.md` | `.claude/skills/eval-research/SKILL.md` |
| `templates/skills/eval-grade/SKILL.md` | `.claude/skills/eval-grade/SKILL.md` |

## Install notes

- The rules directory ships empty except for the format doc and template: the target repo writes its own rules. Rule CONTENT is domain work; this component brings only the FORMAT and the machinery.
- `python scripts/validate_rules.py` must exit 0 before any rules change lands; it regenerates `rules/coverage.md`, which is generated and never hand-edited.
- Evaluations live in `evaluations/<YYYY-MM-slug>/` with stage docs `00-intake.md`, `10-research.md`, `20-package.md`, `30-grading.md`, `40-review.md` and status in `meta.yaml` (statuses: `intake`, `research`, `grading`, `revision`, `review`, `accepted`, `rejected`, `parked`).
- The revision loop is bounded at two round-trips; after that everything unresolved escalates to the maintainer with the ambiguity stated.

## Changelog

- 1.0.0 (2026-07-14): initial release.
