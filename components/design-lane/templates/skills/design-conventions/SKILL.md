---
name: design-conventions
description: The non-negotiables for any design-system or UI-copy change. Voice rules, color rationing, consolidation discipline, the verification bar. Use before editing the design system, writing any string the product ships, or implementing visual work.
---

# Design conventions: the rules that keep the sheet lawful

`{{DESIGN_SYSTEM_PATH}}` is visual law: extend and get approval there first, then implement. This skill is the checklist for working on or against it; rationale lives in `docs/decisions.md` and the sheet's own annotations, nowhere else.

## Voice: every string the product ships

The sheet's **Voice & microcopy** section is the law; its rules bind every shipped string. Scope boundaries: sheet prose and internal docs stay normal writing; user-authored and agent-authored content is not app copy, leave it. Universal starters (the sheet holds the project's full ruled list):

- **Say less.** Helper text only when the affordance cannot speak for itself; default none.
- **Calm register.** Sentence case; no all-caps or mono "AI-tell" labels; no urgency theatrics; state the thing, do not perform it.
- **No rationale on screen.** Never cite decision ids in UI; rationale lives in docs.
- **Labels come from one source module.** No view invents status strings; the label map in code is the single home (one fact, one home applied to copy).

Check every new string against the sheet's voice section before committing; voice violations are the most-broken class of design rule.

## Color: ration the meaning-hue

- A meaning-hue means exactly one thing, project-wide; the sheet's Color section records what. When color stops meaning one thing it stops meaning anything.
- Palette expansion is a maintainer-only ruling. Propose; never add a hue or a token as a side effect of a component change.
- Motion is a hue too: reserve animation for genuinely live things, and let stillness mark settled states.

## Consolidation: one home per component

- One sheet section owns each component's full treatment; every other section points at it, never re-specifies. Shared grammars (states, chips, labels) get their own owning section.
- Before adding a section, check whether an existing one already owns the component; extend it in place. Duplicate demos rot.
- New CSS uses existing tokens only. A new token is a maintainer question, not a default.

## Verification bar

- Conformance = **computed styles + interaction vs the sheet's box, in every theme the product ships** (the sheet's toggle), not vibes and not screenshots alone.
- Platform rendering (scrollbars, native chrome, font hinting) needs a real browser on the target OS; headless rendering lies about it.
- Say plainly what was eyeballed vs computed-verified vs not checked; never claim a check you did not run (evidence or no verdict).

## Known laws quick list

As the repo accumulates visual rulings, keep a one-line-each list here (with D-numbers) of the ones agents keep re-breaking. Starts empty; entries earn their place the same way constitution lines do, by the second violation.
