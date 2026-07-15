# agency-setup build plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [x]`) syntax for tracking. This is a documentation/template repo: "tests" are mechanical scans, not unit tests.

**Goal:** Build the agency-setup process library per `docs/specs/2026-07-14-agency-setup-design.md`.

**Architecture:** Three layers: doctrine (why), components (installables), SETUP.md router (interview + install). Self-hosted memory core in docs/.

**Tech Stack:** Markdown throughout; one stdlib-only Python script (`validate_rules.py`); one GitHub Actions workflow; one POSIX pre-commit hook.

## Global constraints

- No em dashes in any file (workspace rule). Verify: `grep -rn $'\xe2\x80\x94' --include="*.md" --include="*.py" --include="*.yml" .` returns nothing.
- Person-agnostic: no maintainer names, product names, or domain content from source repos. Verify with grep for known-specific terms.
- Placeholders in component templates use `{{NAME}}`; every placeholder is documented in that component's COMPONENT.md.
- Component versions start at 1.0.0; registry table in `components/README.md` matches every COMPONENT.md.
- No git commit without in-the-moment maintainer approval (workspace floor).

---

### Task 1: Doctrine layer

**Files:** Create `doctrine/README.md`, `doctrine/amendments.md`, `doctrine/P01-repo-is-memory.md` through `doctrine/P10-fresh-context-isolation.md`.

- [x] Write README (article format, amendment rule), amendments log seeded with A1 (adoption of P01..P10), ten articles each with Statement / Rationale / What breaks without it.
- [x] Verify: every article has the three sections; no em dashes.

### Task 2: Core components (memory-core, claude-md-skeleton, gateway)

**Files:** Create `components/README.md` (registry), `components/memory-core/COMPONENT.md` + 4 templates, `components/claude-md-skeleton/COMPONENT.md` + template, `components/gateway/COMPONENT.md` + agent charter + skill.

- [x] Write registry table with all 9 components.
- [x] Write each COMPONENT.md (version, installs-to paths, placeholders, dependencies) and templates.
- [x] Verify: placeholders used in templates all appear in the owning COMPONENT.md.

### Task 3: Dev components (dev-lanes, review-law, steward)

**Files:** Create `components/dev-lanes/*` (builder charter, coding-handoff skill, parallel-lanes skill), `components/review-law/*` (REVIEW.md template, reviewer charter, PR template), `components/steward/*` (process-steward skill).

- [x] Generalize source procedures: strip repo-specific law references, keep the mechanics (per-commit gates, squash discipline, draft-PR registry, severity calibration, audit checks).
- [x] Verify: no source-repo decision numbers or product names remain.

### Task 4: Eval + design + CI components

**Files:** Create `components/gradable-rules/*` (rules README, article template, amendments template, `validate_rules.py`, eval-intake/research/grade/run skills), `components/design-lane/*`, `components/ci-gates/*` (docs-lint.yml, pre-commit hook).

- [x] validate_rules.py: stdlib only; checks frontmatter + required sections per rule article; regenerates coverage table; exit 1 on violation.
- [x] Run `python validate_rules.py` against a scratch copy of the article template filled in, confirm exit 0; against a broken copy, confirm exit 1.
- [x] ci-gates: word-budget check, forbidden-phrasing check for STATE.md, PR title grammar; local hook mirrors the same checks.

### Task 5: Router, profiles, harvest

**Files:** Create `SETUP.md`, `profiles/README.md` + 4 profile files, `setup/harvest.md`.

- [x] SETUP.md: interview script (5 questions, recommendation-first), profile resolution, install procedure (copy, placeholder fill, provenance stamp, manifest write, CLAUDE.md + STATE.md generation), upgrade mode, handoff.
- [x] Profiles: component list + rationale + follow-up questions + first-session guidance each.
- [x] Harvest: manifest read, drift diff, decision/journal mining, amendment proposal format.
- [x] Verify: every component named in profiles exists in registry; SETUP.md references only files that exist.

### Task 6: Root + self-hosted docs

**Files:** Create `README.md`, `CLAUDE.md` (budget 400 words), `.gitignore`, `docs/STATE.md`, `docs/journal.md`, `docs/decisions.md` (seed D1..D4 from design decisions), `docs/open-questions.md`.

- [x] Verify: CLAUDE.md word count ≤ 400 (`wc -w`).

### Task 7: Full verification + handoff

- [x] Em-dash scan across all files: zero hits.
- [x] Placeholder-leak scan: `{{` appears only inside `components/*/templates/` and SETUP.md examples.
- [x] Person-specific scan: grep for source-repo names, maintainer identifiers, product names; zero hits outside this plan's allowed generic phrasing.
- [x] `git add -A`, show `git status`, propose commit message, wait for approval (workspace floor rule).
