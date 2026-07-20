# {{PROJECT_NAME}} design system

Generated from `design-system.html` by `scripts/generate_design_md.py`. Never hand-edit;
the sheet is the source of truth, and this file exists so agents can read and cite the law
without parsing HTML. Demos, exact component rendering, and conformance checks live in the
sheet only.

## Tokens

| token | light | dark | note |
|---|---|---|---|
| `--background-1` | `#f7f6f4` | `#151412` | the page |
| `--background-2` | `#ffffff` | `#1e1d1a` | raised surfaces: cards, inputs, menus |
| `--gray-100` | `#f2f1ee` | `#242320` |  |
| `--gray-200` | `#eceae6` | `#2a2926` |  |
| `--gray-300` | `#e2e0da` | `#33322d` |  |
| `--gray-400` | `#d7d4cd` | `#3e3c36` |  |
| `--gray-500` | `#c2beb5` | `#4c4a43` |  |
| `--gray-600` | `#a5a096` | `#615e55` |  |
| `--gray-700` | `#8a857b` | `#817d72` |  |
| `--gray-800` | `#6e6960` | `#9d988c` |  |
| `--gray-900` | `#55514a` | `#c3bfb4` |  |
| `--gray-1000` | `#22201c` | `#edebe4` |  |
| `--brand` | `#4a6b52` | `#7fa88a` | the product's hand: primary action, selection |
| `--brand-hover` | `#405e48` | `#8fb599` |  |
| `--brand-ink` | `#ffffff` | `#171613` | text on brand |
| `--accent` | `#b98a2f` | `#d3a94e` | the one reserved meaning-hue; ration it (see Color) |
| `--font-sans` | `ui-sans-serif, system-ui, -apple-system, "Segoe UI", sans-serif` | `` |  |
| `--font-mono` | `ui-monospace, "Cascadia Code", Consolas, monospace` | `` |  |
| `--type-title` | `600 1.375rem/1.3 var(--font-sans)` | `` | tracking -0.02em |
| `--type-section` | `600 1rem/1.4 var(--font-sans)` | `` | tracking -0.01em |
| `--type-body` | `400 0.875rem/1.6 var(--font-sans)` | `` |  |
| `--type-label` | `500 0.8125rem/1.4 var(--font-sans)` | `` |  |
| `--type-caption` | `400 0.75rem/1.5 var(--font-sans)` | `` |  |
| `--type-data` | `400 0.78rem/1.5 var(--font-mono)` | `` |  |
| `--space-1` | `4px` | `` |  |
| `--space-2` | `8px` | `` |  |
| `--space-3` | `12px` | `` |  |
| `--space-4` | `16px` | `` |  |
| `--space-6` | `24px` | `` |  |
| `--space-8` | `32px` | `` |  |
| `--space-10` | `40px` | `` |  |
| `--space-16` | `64px` | `` |  |
| `--radius-s` | `6px` | `` | controls, inputs, chips |
| `--radius-m` | `12px` | `` | cards, menus, modals |
| `--radius-full` | `9999px` | `` | pills, avatars |
| `--content-max` | `72rem` | `` | reading column cap; swap the value, keep the role (see Layout) |
| `--shadow-raised` | `0 1px 2px rgba(26, 23, 18, 0.04), 0 2px 4px rgba(26, 23, 18, 0.04)` | `0 1px 2px rgba(0, 0, 0, 0.3), 0 2px 4px rgba(0, 0, 0, 0.3)` |  |
| `--shadow-float` | `0 1px 1px rgba(26, 23, 18, 0.02), 0 4px 8px -4px rgba(26, 23, 18, 0.06), 0 16px 24px -8px rgba(26, 23, 18, 0.08)` | `0 1px 1px rgba(0, 0, 0, 0.2), 0 4px 8px -4px rgba(0, 0, 0, 0.4), 0 16px 24px -8px rgba(0, 0, 0, 0.5)` |  |
| `--ease` | `cubic-bezier(0.2, 0.8, 0.3, 1)` | `` |  |
| `--duration-state` | `150ms` | `` | hovers, presses |
| `--duration-reveal` | `200ms` | `` | menus, popovers |
| `--duration-overlay` | `300ms` | `` | modals, drawers |
| `--focus-ring` | `0 0 0 2px var(--background-2), 0 0 0 4px var(--brand)` | `` |  |

## How this sheet works

One section per foundation or component, each a boxed demo with a one-paragraph annotation stating the law it carries. Foundations first (Color, Type, Iconography, Spacing, Shape and elevation, Motion, Layout and scroll, Voice), then shared grammars (state, overlays), then components. One home per component: extend a section in place rather than adding a duplicate. Every demo must render correctly in both themes (the toggle above), and conformance against this sheet means computed styles and interaction, not vibes. Components reference tokens only; if a value is not a token, it does not ship.

## Components: reference the library

Foundations above are always owned law; they theme the component library. Components come from the project's component library by default, the way a working designer defaults to the company's system: a component section names the library component, states which tokens theme it, and records only the deltas (the variants and states this product uses, and what the component means here). It never re-draws a primitive the library ships; that copy is the drift this sheet exists to prevent, and the real themed component in the app is the conformance target. Hand-drawing is the exception, not a mode, and both cases are escalations: a product-specific component the library does not ship is composed from library primitives first and drawn fresh only when composition cannot express it; a stack with no vetted library is a gap flagged for source intake, not a quiet fallback. When a library component cannot do what a design needs, the constraint goes to the maintainer with options; nobody silently builds around the library.

- Default: a component section is a reference plus deltas; conform against the themed library component in the app, not a copy in this sheet.
- Exception, escalated: product-specific components compose from library primitives first; fully hand-drawn sections exist only where composition cannot express the design (the Controls section below shows the drawn-section pattern for that case, and for pre-establishment starters).
- Foundations (color, type, icons, spacing, shape, motion, layout, overlays, voice, status) stay owned law in every case and drive the library's theme.

## Color

One gray ramp carries the whole interface, and the step number encodes the job: 100 to 300 are tinted fills and hovers, 400 to 600 are borders, 700 to 800 are muted foreground, 900 to 1000 are text. Rank information with the ramp before reaching for a hue. Meaning-color is rationed: brand marks the product's hand (one filled action per surface), the accent means exactly one thing project-wide (record what, here, when ruled), and state is never signaled by color alone. Palette expansion is a maintainer-only ruling; propose, never add.

- Text on its background keeps at least 4.5:1 contrast, both themes.
- Interaction states step along the ramp (fill 100 to 200 to 300, border 400 to 500 to 600), never invent an off-ramp value.

## Type

Two families: the sans for everything, the mono for code, data, and token names. Each role sets size, weight, line-height, and tracking together as one token; components apply a role, never hand-set properties. Large sizes tighten tracking; body never does. At most two weights per view. Families come from an open-source catalog (Google Fonts is the default pool), license-clean, and are self-hosted (vendored or via a package like fontsource), never linked from a runtime CDN. A brand face is chosen at establishment by rendering two or three real candidates as specimens and ruling on sight, not picked from a name; the starter tokens below fall back to system fonts until that ruling lands.

- Families are open-source (OFL or Apache), self-hosted, no runtime CDN link; the choice is a maintainer ruling.
- Where a surface cannot load the webfont (a browser-tab icon, an OG image, some email clients), never hand the brand face to a bare `serif`/`sans-serif` fallback: bake the shape or accept the system fallback on purpose.
- Roles are tokens: apply `--type-*`, never set size, weight, or tracking on a component by hand.

## Iconography

One icon set for the whole product, from an open-source library (Material Symbols is the default recommendation); the set is chosen at establishment and swapped there, never mixed two at a time. Glyphs ship as inlined path data in a `<use>` symbol library, at one ruled weight matched to the type, drawing color from `currentColor`; never a webfont, and never a hand-drawn glyph when the library already carries it. Third-party marks (a vendor's logo) are the one exception: use that vendor's official asset, note its license, and keep its own color. The shapes below are placeholders that teach the mechanic, not a shipped set.

- One library, one weight, inlined as `<symbol>` + `<use>`; `currentColor` so a glyph inherits its context. No icon font.
- Never hand-draw a glyph the chosen library carries; a custom path is a maintainer question.
- An icon-only control carries an accessible label, and a glyph is never the sole carrier of meaning (pair it with a word, per the state rule).
- Third-party marks: official asset only, license recorded, own color kept; they do not follow the single-set recipe.

## Spacing

A 4px base scale, and a rhythm: 8 inside a group, 16 between groups, 32 between sections. Cards pad 24. If a gap is not on the scale, the layout is guessing.

## Shape and elevation

Two radii plus the pill: 6 for controls and inputs, 12 for cards and menus. Never mix rounded and sharp corners in one view. Elevation is a ramp of layered low-alpha shadows: raised for cards, float for menus and popovers. A tier beyond float is a ruling.

## Motion

Nothing animates by default; motion exists to clarify a change, never to decorate. When it earns its place: one easing, three durations (150ms state changes, 200ms reveals, 300ms overlays), and reduced-motion preferences are always honored. Reserve continuous animation for genuinely live things; stillness is how settled states read as settled.

## Layout and scroll

One scroll region per surface. The page column owns vertical scroll; a view never nests a second scrollbar inside the first, and a horizontal scrollbar never ships (content wraps or truncates instead). When a panel must scroll its own body (a modal, a side rail, a long list), it owns exactly one internal scroll region with the header and footer pinned outside it, and the container never clips a child that overflows on purpose (a popover, a tooltip). The reading column is capped at `--content-max` and centered with symmetric gutters, so proportions hold from a laptop to an ultrawide.

- One vertical scrollbar per surface; zero horizontal scrollbars.
- A scrolling panel pins head and foot; the body is the sole scroll region (flex column, `min-height: 0` on the scroll child).
- A container that hosts an overlay sets no clipping `overflow` on the axis the overlay escapes.
- Reading column: `max-width: var(--content-max)` with `margin-inline: auto`; gutters scale, the column does not sprawl.

## Voice & microcopy

This section is law for every string the product ships. Sheet prose and internal docs stay normal writing; user-authored and agent-authored content is not app copy and is out of scope. Starters below are near-universal; add the project's own rules as they get ruled, and keep the list short enough to check against.

- **Say less.** Helper text only when the affordance cannot speak for itself; default none.
- **Calm register.** Sentence case everywhere; no all-caps labels; no urgency theatrics; state the thing, do not perform it.
- **Controls say what they do.** Verb plus object ("Save changes"), the same name through the whole flow; never "OK" or "Submit".
- **Errors direct, never apologize.** What happened plus the next step.
- **Empty states match the scenario.** An accomplishment can read calm and positive, a blank slate points to the first action, a filtered-empty says what hid the rows; never force cheer where the moment does not carry it.
- **Punctuation is calm too.** No em dashes and no semicolons in shipped copy; periods, colons, commas, and parentheses carry the load (the dash and semicolon stay marks for docs, not product).
- **Confirmations speak in the future.** A confirm names what will happen on confirm ("17 tasks will move"), never the present tense that reads as already done.
- **One fact per surface.** Adjacent copy (a banner and the dialog it opens, a title and its body) never restate each other; each carries a distinct fact.
- *(Add the project's ruled voice rules here, one line each.)*

## Status grammar

Placeholder until the product has states. When it does, this section becomes the one home for every state's full treatment (color, glyph, motion, label), and every other section points here instead of re-specifying a state. Labels come from one source module in code; no view invents status strings. State is never color alone: pair every state hue with a glyph or word.

## Overlays

The one home for overlay behavior; every menu, popover, and tooltip follows it and no component re-specifies it. An overlay renders in the top layer (a portal), positioned fixed off its trigger's rect, not inside the scrolling content that spawned it. It flips across the trigger when it would cross a viewport edge and clamps sideways to stay on screen; its own body is capped and scrolls internally past that cap. It dismisses on outside pointer-down and on Escape (the topmost overlay only), and returns focus to the trigger. Modals sit on this grammar too, with the pinned head and foot from Layout and scroll.

- Portal to the top layer; position fixed off the trigger rect; never clipped by an ancestor's `overflow`.
- Flip on the cross axis at a viewport edge; clamp on the main axis; cap the body height and scroll it internally.
- Dismiss on outside pointer-down and Escape (topmost only); focus returns to the trigger.
- A re-measure never resets the body's scroll position: internal scroll and outside scroll are handled apart (the bug that makes a long menu un-scrollable).

## Controls

The example component, and the pattern every new section follows: full component, all variants and every state in one demo, spec notes underneath. Primary is the only brand-filled control on a surface; everything else ranks by the gray ramp.

- Heights: 36px default, 30px small; label role type; radius `--radius-s`.
- Hover and press step along the ramp (`gray-100`, `gray-200`; border `400` to `500`); primary darkens to `--brand-hover`.
- Focus is the two-layer ring (`--focus-ring`) on `:focus-visible`, on every focusable thing, both themes.
- Disabled is the `gray-100` fill with `gray-700` text, never an opacity trick.
