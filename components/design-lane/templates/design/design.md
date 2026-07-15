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
| `--shadow-raised` | `0 1px 2px rgba(26, 23, 18, 0.04), 0 2px 4px rgba(26, 23, 18, 0.04)` | `0 1px 2px rgba(0, 0, 0, 0.3), 0 2px 4px rgba(0, 0, 0, 0.3)` |  |
| `--shadow-float` | `0 1px 1px rgba(26, 23, 18, 0.02), 0 4px 8px -4px rgba(26, 23, 18, 0.06), 0 16px 24px -8px rgba(26, 23, 18, 0.08)` | `0 1px 1px rgba(0, 0, 0, 0.2), 0 4px 8px -4px rgba(0, 0, 0, 0.4), 0 16px 24px -8px rgba(0, 0, 0, 0.5)` |  |
| `--ease` | `cubic-bezier(0.2, 0.8, 0.3, 1)` | `` |  |
| `--duration-state` | `150ms` | `` | hovers, presses |
| `--duration-reveal` | `200ms` | `` | menus, popovers |
| `--duration-overlay` | `300ms` | `` | modals, drawers |
| `--focus-ring` | `0 0 0 2px var(--background-2), 0 0 0 4px var(--brand)` | `` |  |

## How this sheet works

One section per foundation or component, each a boxed demo with a one-paragraph annotation stating the law it carries. Foundations first (Color, Type, Spacing, Shape and elevation, Motion, Voice), then the state grammar, then components. One home per component: extend a section in place rather than adding a duplicate. Every demo must render correctly in both themes (the toggle above), and conformance against this sheet means computed styles and interaction, not vibes. Components reference tokens only; if a value is not a token, it does not ship.

## Color

One gray ramp carries the whole interface, and the step number encodes the job: 100 to 300 are tinted fills and hovers, 400 to 600 are borders, 700 to 800 are muted foreground, 900 to 1000 are text. Rank information with the ramp before reaching for a hue. Meaning-color is rationed: brand marks the product's hand (one filled action per surface), the accent means exactly one thing project-wide (record what, here, when ruled), and state is never signaled by color alone. Palette expansion is a maintainer-only ruling; propose, never add.

- Text on its background keeps at least 4.5:1 contrast, both themes.
- Interaction states step along the ramp (fill 100 to 200 to 300, border 400 to 500 to 600), never invent an off-ramp value.

## Type

Two families: the sans for everything, the mono for code, data, and token names. Each role sets size, weight, line-height, and tracking together as one token; components apply a role, never hand-set properties. Large sizes tighten tracking; body never does. At most two weights per view.

## Spacing

A 4px base scale, and a rhythm: 8 inside a group, 16 between groups, 32 between sections. Cards pad 24. If a gap is not on the scale, the layout is guessing.

## Shape and elevation

Two radii plus the pill: 6 for controls and inputs, 12 for cards and menus. Never mix rounded and sharp corners in one view. Elevation is a ramp of layered low-alpha shadows: raised for cards, float for menus and popovers. A tier beyond float is a ruling.

## Motion

Nothing animates by default; motion exists to clarify a change, never to decorate. When it earns its place: one easing, three durations (150ms state changes, 200ms reveals, 300ms overlays), and reduced-motion preferences are always honored. Reserve continuous animation for genuinely live things; stillness is how settled states read as settled.

## Voice & microcopy

This section is law for every string the product ships. Sheet prose and internal docs stay normal writing; user-authored and agent-authored content is not app copy and is out of scope. Starters below are near-universal; add the project's own rules as they get ruled, and keep the list short enough to check against.

- **Say less.** Helper text only when the affordance cannot speak for itself; default none.
- **Calm register.** Sentence case everywhere; no all-caps labels; no urgency theatrics; state the thing, do not perform it.
- **Controls say what they do.** Verb plus object ("Save changes"), the same name through the whole flow; never "OK" or "Submit".
- **Errors direct, never apologize.** What happened plus the next step; an empty state points to the first action.
- *(Add the project's ruled voice rules here, one line each.)*

## Status grammar

Placeholder until the product has states. When it does, this section becomes the one home for every state's full treatment (color, glyph, motion, label), and every other section points here instead of re-specifying a state. Labels come from one source module in code; no view invents status strings. State is never color alone: pair every state hue with a glyph or word.

## Controls

The example component, and the pattern every new section follows: full component, all variants and every state in one demo, spec notes underneath. Primary is the only brand-filled control on a surface; everything else ranks by the gray ramp.

- Heights: 36px default, 30px small; label role type; radius `--radius-s`.
- Hover and press step along the ramp (`gray-100`, `gray-200`; border `400` to `500`); primary darkens to `--brand-hover`.
- Focus is the two-layer ring (`--focus-ring`) on `:focus-visible`, on every focusable thing, both themes.
- Disabled is the `gray-100` fill with `gray-700` text, never an opacity trick.
