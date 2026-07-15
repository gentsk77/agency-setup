---
name: parallel-lanes
description: Conventions for running multiple concurrent workstreams. Lane registry via draft PRs, stacked phase branches, integration-branch assembly, shared-file region ownership, merge-forward discipline. Use when dispatching 2+ parallel lanes or assembling a multi-branch wave.
---

# Parallel lanes: multi-workstream conventions

## Lane registry: draft PRs

- Every lane opens a **draft PR at branch creation**, not at review time. The PR list is the live registry of in-flight lanes; no branch-map docs, no memory notes (one fact, one home).
- The draft body starts as the lane's one-paragraph scope plus its file-ownership claim; it fills out to full template shape before ready.
- **Ready-for-review is the signal to the gateway:** mark ready only when gates are green and the branch is rebased onto its trunk.

## Branch topology

- **Independent lanes** branch off the trunk and merge via their own PRs.
- **Dependent phases stack:** `phase-2` branches off `phase-1`. A fix found in an earlier phase lands on that phase's branch and **merges forward** through the stack; never patch a downstream copy.
- **Waves** (3+ coordinated branches) assemble on `integration/<wave>`: phases merge in dependency order, the maintainer tests the assembled trunk, fixes land as reviewed PRs into the integration branch, then one wave PR to the trunk carrying every tracker close.

## Shared files: region ownership

- The handoff declares a **file-ownership map up front**: each lane lists the files it owns; a shared file is split into named regions, one owner each.
- A lane never edits another lane's region; cross-region need gets flagged to the gateway, not reached for.
- Each lane rebases onto the current trunk before ready-for-review; conflicts are the rebaser's to resolve.
