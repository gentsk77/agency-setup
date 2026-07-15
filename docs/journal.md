# Journal: agency-setup

Session log, reverse-chronological, append-only.

---

## 2026-07-14 (later): design-lane 1.1.0

Maintainer review caught a real gap: 1.0.0 shipped the proposal lifecycle without saying how a design system gets established, and without the conventions checklist. Audit against field practice confirmed. Added: starter design-system.html (neutral tokens, theme toggle, foundations sections, example component), a generalized design-conventions skill (voice / color rationing / consolidation / verification categories), and an enriched design-proposals skill (establishment-by-consolidation procedure, verbatim CSS-reuse rule, home-section convergence map, dropped status, definition-of-done). First proof of the harvest direction: library gaps surface by holding components against live practice.

---

## 2026-07-14: founding session

Distilled the working process from two field-tested repos (a product-development repo and an evaluation-pipeline repo) into this library. Interview settled four structural rulings (D1 to D4). Built: doctrine P01 to P10 with amendment log, nine components at 1.0.0 (memory-core, claude-md-skeleton, gateway, dev-lanes, review-law, steward, gradable-rules, design-lane, ci-gates), four profiles, the SETUP.md router, and the harvest procedure. `validate_rules.py` tested against good and broken articles (exit 0 / exit 1 verified). Design doc and build plan in `docs/specs/` and `docs/plans/`.
