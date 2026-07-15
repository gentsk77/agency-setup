---
name: design-proposals
description: How design changes stage, get approved, get implemented, and converge into the design system. Use when capturing a design session as a proposal, implementing an approved proposal, or checking whether a visual change conforms.
---

# Design proposals: the lifecycle

`{{DESIGN_SYSTEM_PATH}}` is the visual source of truth for **built** design. Unbuilt design never edits it directly.

## The lifecycle

1. **Stage.** A design session's output becomes a proposal package in `design/proposals/<slug>/`: the mock or spec, the rationale, and the design-system sections it would change. Status: `draft`.
2. **Approve.** The maintainer approves the proposal (status: `ready-for-eng`). The proposer never self-approves.
3. **Implement.** The implementing lane builds against the proposal. Conformance means computed styles and interaction match the proposal, not vibes.
4. **Converge.** In the same change that ships the implementation: fold the proposal's content into `{{DESIGN_SYSTEM_PATH}}` (it now describes built reality) and archive the proposal folder. The sheet and the app never disagree for longer than one merge.

## Invariants

- Extend the design system and get approval first, then implement; never the reverse.
- Verify every drawn component in every theme the product ships; a component verified in one theme is unverified.
- Behavior-verified-but-nonconforming is a failure, not a partial pass.
- Visual PRs name the design-system sections they conform to.
