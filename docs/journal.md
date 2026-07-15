# Journal: agency-setup

Session log, reverse-chronological, append-only.

---

## 2026-07-14 (evening): design-lane 1.3.0, generated design.md

Maintainer asked whether the sheet should have an agent-readable design.md twin, with the two kept in sync. Answer: yes, but generated, never hand-maintained (the coverage.md pattern). Added `scripts/generate_design_md.py`: parses the sheet's token block and section structure, emits design.md (token table with light and dark values, per-section law text); `--check` mode fails when stale, wired into ci-gates install notes. Sheet stays the sole source of truth and conformance target. Tested: generate, in-sync check, drift detection, multi-declaration token lines.

---

## 2026-07-14 (later still): design-lane 1.2.0, taste pass on the starter sheet

Studied a public reference system (Vercel Geist) and folded its mechanics into the starter sheet: intent-encoded gray ramp, role-token typography, spacing rhythm, layered elevation ramp, motion law, full control-state law with a two-layer focus ring, accessibility floor. Reference's Title Case convention deliberately rejected (calm sentence-case register is ruled taste here). Verified in browser, both themes.

---

## 2026-07-14 (later): design-lane 1.1.0

Maintainer review caught a real gap: 1.0.0 shipped the proposal lifecycle without saying how a design system gets established, and without the conventions checklist. Audit against field practice confirmed. Added: starter design-system.html (neutral tokens, theme toggle, foundations sections, example component), a generalized design-conventions skill (voice / color rationing / consolidation / verification categories), and an enriched design-proposals skill (establishment-by-consolidation procedure, verbatim CSS-reuse rule, home-section convergence map, dropped status, definition-of-done). First proof of the harvest direction: library gaps surface by holding components against live practice.

---

## 2026-07-14: founding session

Distilled the working process from two field-tested repos (a product-development repo and an evaluation-pipeline repo) into this library. Interview settled four structural rulings (D1 to D4). Built: doctrine P01 to P10 with amendment log, nine components at 1.0.0 (memory-core, claude-md-skeleton, gateway, dev-lanes, review-law, steward, gradable-rules, design-lane, ci-gates), four profiles, the SETUP.md router, and the harvest procedure. `validate_rules.py` tested against good and broken articles (exit 0 / exit 1 verified). Design doc and build plan in `docs/specs/` and `docs/plans/`.
