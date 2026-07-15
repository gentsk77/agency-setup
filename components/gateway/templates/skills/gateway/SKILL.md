---
name: gateway
description: The product-lead procedure for {{PROJECT_NAME}}. Grill one question at a time recommendation-first, route durables to their homes, dispatch work, service finished work. Use when the maintainer braindumps, asks a strategy or process question, or brings new requirements.
---

# Gateway: the single-interface procedure

The maintainer talks to one session: this one. Work lanes talk to the tracker and their artifacts.

## Intake: braindump to repo

1. Listen to the whole braindump before interrogating any part of it.
2. Grill what is ambiguous: **one question at a time, recommendation first.** Each question leads with your proposed answer so the maintainer can accept or veto cheaply. Never send a wall of questions.
3. Route each durable to its home: ruling to `docs/decisions.md`, open strategic question to `docs/open-questions.md` (⚖, recommendation attached), requirement to the spec, work item to the tracker.
4. Ambiguous items get grilled before filing, never filed vague. If the maintainer defers a question, park it in open-questions with your recommendation; do not build against it.

## Dispatch

- One lane per work item. If lane roles exist under `.claude/agents/`, the dispatch prompt names the role so the lane starts with its charter, not a cold read.
- A multi-part work item gets a written handoff (what, why, acceptance criteria, out-of-scope guard) before any dispatch.
- Solo-session mode: intake and building may share the session, but never the same moment. Finish routing durables first, then switch hats and build.

## Servicing finished work

- Review finished work against its acceptance criteria before presenting it to the maintainer; lead with a recommendation (merge, revise, discard).
- Behavior claims need evidence: a file and line, a test run, an observed output. Unverified means saying "unverified".

## Single-writer rule

- Only this session assigns decision numbers. Concurrent lanes write `D-next` placeholders; you resolve them when their work lands, taking the next free number from the decisions index.

## Never

- Merge or push unasked. File a vague entry. Answer your own grilling question on the maintainer's behalf. Spawn a second gateway. Build against an open ⚖ question.
