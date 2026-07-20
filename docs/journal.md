# Journal: agency-setup

Session log, reverse-chronological, append-only.

---

## 2026-07-18: design-lane 1.5.0, components-by-default (D8)

While walking the maintainer through how a mock gets routed, the component-library question surfaced. First cut made library adoption an optional establishment mode (draw or reference, adopt-or-not); the maintainer redirected it hard, and rightly: real designers do not ask their PM whether to follow the company brand and component library, so the posture is the default, not a question. Final model, filed as D8: when design-lane installs, SETUP.md always carries the matching vetted sources into the target manifest as its default component stack; establishment asks one fork (full design system now vs low-fi first, with the standing expectation that a serious product graduates) and, when establishing, asks only **which** library, leading with the recorded default; the sheet's foundations theme the library; component sections reference the themed component plus deltas and never re-draw primitives; hand-drawing survives only as an escalated exception (compose from primitives first; no-library stacks flag a source-intake gap); library constraints escalate to the maintainer with options, never silently built around. design-lane to 1.5.0 across the sheet law, both skills, the charter, SETUP.md, and sources.md. design.md regenerated, `--check` green, var-gate clean. The branch was consolidated into clean commits at the maintainer's ask (the intermediate draw-or-reference cut has no commit of its own; this entry records it).

## 2026-07-18: adopt PR-only trunk (D7), work moved to a PR

Committed the taste harvest and source intake straight to `main` by habit, which is exactly the failure the maintainer then asked to prevent. Retroactively branched the two commits to `feat/taste-harvest-source-intake`, rewound local `main` to `origin/main`, and opened them as a PR for review. Filed D7: agency-setup dogfoods the `review-law` it ships, so `main` is PR-only henceforth. Intended to enforce with GitHub branch protection, but the API returned 403: a private repo on the free plan gates both classic branch protection and rulesets behind Pro or going public. Fell back to a tracked client-side hook (`scripts/hooks/pre-commit` + `pre-push`, enabled per clone via `git config core.hooksPath scripts/hooks`), proven to block commits and pushes to `main` while allowing branches. Server-side enforcement is left as an open maintainer call (public vs. Pro vs. hook-only). CLAUDE.md's Git invariant and STATE updated; this governance change rides the same PR as its later commits.

## 2026-07-18: design-lane 1.4.0 (taste harvest) + source intake procedure (D5, D6)

Maintainer reported the design agent on a live install lacked taste: em dashes and off-voice copy, weak font choices, weak glyphs, multiple-scrollbar and other non-modern web patterns. Read the install's journal and decisions: every complaint was already a hard-won ruling there (font rounds and a serif self-host; a whole icon-set migration to inlined Material Symbols; modal and popover single-scroll-region fixes; a voice sweep banning em dashes then semicolons, plus future-tense confirmations and scenario-matched empty states; a silent undefined-`var()` failure that shipped twice). Root cause was a library gap, not agent stupidity: the starter sheet shipped categories without taste, so establishment-by-redline made the first install re-teach the universal classes by hand.

Harvested them into `design-lane` 1.4.0 (D5): new Iconography, Layout-and-scroll, and Overlays sections; a type-sourcing law (open-source, self-hosted, ruled on rendered specimens) with the fallback-face trap; four Voice rules; a new `--content-max` token. Mechanized the silent-void bug: `generate_design_md.py` now hard-fails on any `var()` referencing an undefined token, in both modes (proved against a fresh copy with `--space-5` injected: it caught it, exit 1; the real sheet passes and design.md regenerated `--check` green). Skills and the design-lead charter (options-over-prose taste rule) updated to match. Recommendations name specific tooling (Google Fonts, Material Symbols) as swappable defaults; token values stay system-font neutral, so no domain crosses in.

Added the inbound twin of harvest (D6): `setup/sources.md` vets external finds (component libraries, fonts, icon sets) through a license/maintenance/official-channel gate, classifies each as reference, template-amendment candidate, or install-interview option (with a recommended-default tier), and stays propose-only like harvest. First entries are a two-tier component default for React + Tailwind targets, both vetted from their own docs and both under the design-lane sheet. **shadcn/ui** as the recommended base (70+ Radix-based primitives, full coverage including the dialog/form/dropdown/card set, CSS-variable theming, copy-you-own-it via CLI which matches D1's consumption model, MIT); Radix's correct overlay/focus/scroll behavior is the direct answer to the install's overlay and scrollbar complaints. **beUI** re-tiered from "the default" to the recommended **motion layer** on top (51 components, 11 primitives plus 40 motion pieces, installs through the same shadcn-compatible registry so it drops onto the shadcn base; motion-forward, not a full foundation alone). Scope for both verified from component listings rather than taglines. SETUP.md surfaces matching sources during the interview; CLAUDE.md repo map and the intro updated. design-lane registry bumped to 1.4.0.

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
