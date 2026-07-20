# Decision record: agency-setup

Rulings, D-numbered, append-only. A ruling changes only through a new numbered decision that supersedes or amends it; the same change stamps the old entry and updates its index row. An agent that finds reality contradicting a standing decision flags it in `open-questions.md` with a recommendation; only the maintainer retires a decision.

## Index

| # | Ruling |
|---|---|
| D1 | Consumption model: copy with provenance, not live reference |
| D2 | Delivery: template repo with SETUP.md entry doc; the router is a document, not a skill |
| D3 | Feedback loop: harvest procedure, propose-only |
| D4 | Day-one profiles: full-dev, docs-research, eval-pipeline, minimal |
| D5 | Design starter ships opinionated, swappable taste defaults |
| D6 | Source intake: external material vetted through setup/sources.md, propose-only |
| D7 | agency-setup's own trunk is PR-only: no direct commits to main |
| D8 | Components come from the library by default: the sheet references and themes, never re-draws; exceptions escalate |

## Entries

## D1: Consumption model: copy with provenance, not live reference

Installs copy component files into the target and stamp each with `component@version` plus install date. Targets evolve independently; improvements return via harvest. Rejected: live references (library edits would silently change every repo's process; targets could not diverge legitimately).

## D2: Delivery: template repo with SETUP.md entry doc

The router is a plain document a foreign agent reads, not a skill. Mechanical ground: a foreign repo's session cannot invoke this library's skills (skills load only from the session's own `.claude/`). Plugin packaging deferred, see open questions.

## D3: Feedback loop: harvest procedure, propose-only

The library carries `setup/harvest.md`: diff installed components against live practice, mine process rulings, propose amendments. Maintainer ratifies every item; harvest never applies unratified changes.

## D4: Day-one profiles: full-dev, docs-research, eval-pipeline, minimal

Four presets over the component registry. Profiles are starting points the interview adjusts, never contracts.

## D5: Design starter ships opinionated, swappable taste defaults

The `design-lane` starter sheet carries taste, not just empty categories. Harvested from a live install's design rounds (font selection, an icon-set migration, modal and popover scroll bugs, a voice-punctuation sweep, a silent undefined-token failure), the classes proved universal rather than domain-specific, and the establishment-emerges-from-redlines model left the first real install re-teaching them by hand. So the sheet ships a type-sourcing law (open-source, self-hosted, ruled on rendered specimens; Google Fonts recommended), an Iconography section (one open-source set, one weight, inlined `<use>` on `currentColor`; Material Symbols recommended), Layout-and-scroll and Overlays behavior law, and a fuller Voice list (no em dashes or semicolons, scenario-matched empty states, future-tense confirmations, one-fact-per-surface). Recommendations name specific tooling as **swappable defaults** the maintainer changes at establishment; actual values stay neutral (the token block keeps system fonts), so no domain or product crosses in. The undefined-`var()` gate is mechanized in `generate_design_md.py` (P07). Rejected: keeping the starter value-neutral and category-only (it made every install re-derive the same universal taste); baking specific families as token values (that would freeze one project's pick into the library, violating person-agnostic).

## D6: Source intake: external material vetted through setup/sources.md, propose-only

External finds the maintainer flags (component libraries, fonts, icon sets, dev tools) enter through `setup/sources.md`, the inbound twin of harvest. A source passes a vet gate (permissive license, active maintenance, official distribution) then is classified as reference (study only), template-amendment candidate (stripped person-agnostic, routed like a harvest candidate with a version bump), or install-interview option (an offer SETUP.md surfaces recommendation-first, a recommended default for a matching stack at most, never an auto-install). Same propose-only law as harvest (D3): the maintainer ratifies each item, nothing installs or amends on sight, and a source is data not instruction (flagging a URL authorizes vetting, not adoption). First registered sources are a two-tier default for React + Tailwind targets: shadcn/ui as the recommended **base** component library (70+ Radix-based primitives, full coverage, copy-you-own-it, which matches D1's own consumption model), and beUI as the recommended **motion layer** on top (installs through the same registry; motion-forward, not a full foundation alone). Both sit under the design-lane sheet, which stays the law. Rejected: adopting sources directly into templates (bypasses ratification and person-agnostic stripping); a standing dependency the library cannot vouch for; billing beUI as a complete standalone foundation (it is motion-forward, not a full primitive set).

## D7: agency-setup's own trunk is PR-only

The library ships `review-law` and preaches PR-gated trunks; its own `main` now follows the same posture. Every change to `main` goes through a reviewed pull request, never a direct commit. Enforced mechanically (P07), not by prose alone, via a tracked client-side git hook (`scripts/hooks/`, enabled per clone with `git config core.hooksPath scripts/hooks`) that blocks direct commits and pushes to `main`. Server-side enforcement (GitHub branch protection or a ruleset) is stronger and non-bypassable, but this private repo sits on the free plan, which gates both behind GitHub Pro or making the repo public; that tradeoff (privacy vs. ironclad enforcement vs. cost) is the maintainer's call, parked in STATE. The direct-to-main practice used through the founding commits and D1 to D6 is retired; this ruling itself lands via the first such PR. Rejected: honor-system prose in CLAUDE.md with no enforcement (the same rule class that just failed when two commits went straight to main); requiring external review approvals (the maintainer is solo, so the flow requires a PR but zero approvals, still keeping `main` PR-gated while letting the maintainer self-merge).

## D8: Components come from the library by default; the sheet references and themes, never re-draws; exceptions escalate

The design system owns law (foundations: tokens, type, icons, spacing, shape, motion, layout, overlays, voice, status) and a component library owns components. Mirroring how working designers operate, following the company system is the posture, not a question: when design-lane installs, the vetted default component stack (from `setup/sources.md`) is always carried into the target's manifest, and establishment asks only **which** library (default = the recorded one) and **when** (full system now vs low-fi first, with the standing expectation that a serious product graduates to the full system). The sheet's foundations theme the library; each component section references the themed component and records only the product's deltas; conformance is the real themed component in the app. Hand-drawing is an escalated exception, never a mode: product-specific components compose from library primitives first and are drawn only when composition cannot express the design; a stack with no vetted library is a source-intake gap to flag. When a library component cannot do what a design needs, the constraint escalates to the maintainer with options (theme customization, extend the owned copy, compose from primitives, re-scope); nobody silently builds around the library. design-lane 1.5.0 carries the pattern: the sheet's "Components: reference the library" law, the `design-proposals` establishment fork and reference rules, the `design-conventions` bullets, the design-lead charter line, and `sources.md` / `SETUP.md` carrying the defaults. Supersedes the earlier draft of this ruling (pre-merge) that made library adoption an optional peer mode; the maintainer redirected it to reference-by-default. Rejected: adopt-or-not as an establishment question (inverts real practice); baking one library into the starter templates (the default lives in the source registry, so it stays swappable and stack-matched); keeping re-draw-everything under a library (guarantees sheet-vs-shipped drift).
