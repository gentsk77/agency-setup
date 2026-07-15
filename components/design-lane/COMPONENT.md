# Component: design-lane

- **Version:** 1.1.0
- **Requires:** gateway
- **Installs to:** `.claude/agents/design-lead.md`, `.claude/skills/design-conventions/SKILL.md`, `.claude/skills/design-proposals/SKILL.md`, `{{DESIGN_SYSTEM_PATH}}`
- **Placeholders:** `{{DESIGN_SYSTEM_PATH}}` (e.g. `design/design-system.html`), `{{PROJECT_NAME}}`

## What it installs

The design-system-as-law pattern for projects with a visual surface: one artifact is the visual source of truth for **built** design; approved-but-unimplemented design stages as proposals and converges into the source of truth when implemented. Ships the lane charter, the conventions checklist, the establishment + lifecycle procedure, and a starter sheet.

| Template | Target |
|---|---|
| `templates/agents/design-lead.md` | `.claude/agents/design-lead.md` |
| `templates/skills/design-conventions/SKILL.md` | `.claude/skills/design-conventions/SKILL.md` |
| `templates/skills/design-proposals/SKILL.md` | `.claude/skills/design-proposals/SKILL.md` |
| `templates/design/design-system.html` | `{{DESIGN_SYSTEM_PATH}}` |

## Install notes

- Only for repos with a UI or visual output. Skip otherwise; do not install speculatively.
- The starter sheet carries a deliberately neutral placeholder palette, a theme toggle, the foundations sections (Color, Voice & microcopy, Type, Shape and elevation), a Status grammar placeholder, and one example component demonstrating the section pattern. It is a seed, not a finished system: the establishment procedure in the `design-proposals` skill (consolidate the first approved mocks into it, then sheet-first forever) is how it becomes real.
- Product-specific visual law (what the accent hue means, the full voice rule list, state treatments) accumulates in the target's sheet and decisions; this component ships the categories and the discipline, never the values.

## Changelog

- 1.1.0 (2026-07-14): add starter design-system.html; add design-conventions skill (voice/color/consolidation/verification categories, generalized); design-proposals gains the establishment procedure, verbatim CSS-reuse rule for mocks, the handoff template with the home-section convergence map, the `dropped` status, tracker label flow, and the implementation definition-of-done. Gap found reviewing against field practice: 1.0.0 shipped lifecycle skeleton without establishment or conventions.
- 1.0.0 (2026-07-14): initial release.
