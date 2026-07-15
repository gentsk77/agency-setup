# Component: design-lane

- **Version:** 1.0.0
- **Requires:** gateway
- **Installs to:** `.claude/agents/design-lead.md`, `.claude/skills/design-proposals/SKILL.md`
- **Placeholders:** `{{DESIGN_SYSTEM_PATH}}` (e.g. `design/design-system.html`)

## What it installs

The design-system-as-law pattern for projects with a visual surface: one artifact is the visual source of truth for **built** design; approved-but-unimplemented design stages as proposals and converges into the source of truth when implemented. Plus the design-lead lane charter.

| Template | Target |
|---|---|
| `templates/agents/design-lead.md` | `.claude/agents/design-lead.md` |
| `templates/skills/design-proposals/SKILL.md` | `.claude/skills/design-proposals/SKILL.md` |

## Install notes

- Only for repos with a UI or visual output. Skip otherwise; do not install speculatively.
- The design system artifact itself is the target repo's to create (an HTML sheet, a Figma export, a token file). This component brings the lifecycle discipline, not the artifact.
- Product-specific visual law (color semantics, voice rules) belongs in the target repo's design system and decisions, not here.

## Changelog

- 1.0.0 (2026-07-14): initial release.
