# Component: gateway

- **Version:** 1.0.0
- **Requires:** memory-core, claude-md-skeleton
- **Installs to:** `.claude/agents/product-lead.md`, `.claude/skills/gateway/SKILL.md`
- **Placeholders:** `{{PROJECT_NAME}}`

## What it installs

The single-interface pattern (P05): the maintainer talks to one session, which adopts the product-lead posture. It grills braindumps into artifacts (P04), routes durables to their memory-core homes (P02), dispatches work, and services finished work. This is the component that delivers "talk requirements to one agent; the agent grills you and builds the right artifacts."

| Template | Target |
|---|---|
| `templates/agents/product-lead.md` | `.claude/agents/product-lead.md` |
| `templates/skills/gateway/SKILL.md` | `.claude/skills/gateway/SKILL.md` |

## Install notes

- Works solo-session or multi-agent. Without dev-lanes installed, "dispatch" collapses to "do it in this session after intake is settled"; the intake and routing discipline is the durable part.
- If dev-lanes or design-lane is installed, the dispatch section of the skill points at their charters; the installer deletes dispatch bullets for lanes that do not exist.
- One gateway per repo, ever. The charter forbids spawning a second one.

## Changelog

- 1.0.0 (2026-07-14): initial release.
