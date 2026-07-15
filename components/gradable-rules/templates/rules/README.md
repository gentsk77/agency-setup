# Rules

The rulebook candidates are evaluated against. Every active rule is gradable by construction: a human judge and an LLM judge read the same article and can each produce a verdict.

## Article format

One rule per file, named `<ID>.md` (e.g. `R1.md`). Frontmatter carries `id`, `title`, `class` (values | criteria | gate), `kind` (gate | scored), `status` (active | superseded), `version`, `adopted`, `amended_by`. Body carries exactly three sections:

- **Statement.** The rule as prose a person can apply.
- **Grading.** Explicit **PASS**, **FAIL**, and **UNCLEAR** conditions. If graders could read a condition two ways, it is not done.
- **Evidence required.** What the candidate package must contain for this rule to be gradable at all.

Start from `article-template.md`. Run `python scripts/validate_rules.py` before landing any change; it enforces the format and regenerates `coverage.md` (generated, never hand-edited).

## Mutation rule

Amendment only. Adding a rule, superseding a rule, or stamping a superseded rule are the only legal changes, each logged in `amendments.md`. Never edit an adopted article body. Maintainer sign-off is required for every amendment.
