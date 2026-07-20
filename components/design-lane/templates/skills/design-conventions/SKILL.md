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
- **Punctuation is calm too.** No em dashes and no semicolons in shipped copy; periods, colons, commas, parentheses carry it (the dash and semicolon stay docs-register marks).
- **One fact per surface.** Adjacent copy never restates its neighbor; run a content pass, do not echo. Confirmations speak in the future ("will move"), empty states match the scenario rather than forcing cheer.
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
- Components come from the project's component library by default; a component section **references** the themed library component and records only the deltas, never re-drawing a primitive the library ships. Re-drawing what the library owns is the drift you are preventing. Hand-drawn sections are escalated exceptions (product-specific components composed from primitives first; no-library stacks are a source-intake gap to flag). Foundations stay owned law and theme the library.
- When a library component cannot do what the design needs, **escalate the constraint**: say what it cannot do, bring options (theme customization, extend the owned copy, compose from primitives, re-scope), let the maintainer pick. Never silently build around the library.

## Foundations agents keep breaking

Each has a full section in the sheet; this is the one-line reminder, the sheet is the law.

- **Type sourcing.** Families are open-source (OFL/Apache), self-hosted, no runtime CDN; the family is a maintainer ruling made on rendered specimens, not a name. Where a surface cannot load the webfont (tab icon, OG image), do not hand the brand face to a bare system fallback.
- **Icons.** One open-source set, one weight, inlined as `<use>` symbols on `currentColor`; never a webfont, never a hand-drawn glyph the set already carries. Third-party marks keep their official asset and color.
- **Layout and scroll.** One vertical scroll region per surface; zero horizontal scrollbars; a scrolling panel pins head and foot with one internal scroll body; containers never clip overlays.
- **Overlays.** Portal to the top layer, fixed off the trigger, flip and clamp at edges, dismiss on outside-pointer-down and Escape, return focus; a re-measure never resets the body scroll.

## Verification bar

- Conformance = **computed styles + interaction vs the sheet's box, in every theme the product ships** (the sheet's toggle), not vibes and not screenshots alone.
- For referenced components (the default), conform against the **actual themed component in the app**, not a hand-drawn copy in the sheet; the sheet holds the deltas, the app holds the component.
- Platform rendering (scrollbars, native chrome, font hinting) needs a real browser on the target OS; headless rendering lies about it.
- **Sweep every `var()` against the token block before commit.** An undefined token silently voids its whole declaration; where the generator is installed, `generate_design_md.py` fails on this, so run it.
- **A 200 is not render evidence.** Render the asset (favicon, icon, image) and read it; a status code and a content-type do not prove it parsed.
- Say plainly what was eyeballed vs computed-verified vs not checked; never claim a check you did not run (evidence or no verdict).

## Known laws quick list

As the repo accumulates visual rulings, keep a one-line-each list here (with D-numbers) of the ones agents keep re-breaking. Starts empty; entries earn their place the same way constitution lines do, by the second violation.
