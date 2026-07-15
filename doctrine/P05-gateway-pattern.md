# P05: The gateway pattern

## Statement

The maintainer talks to exactly one session per repo: the gateway. The gateway grills, records, dispatches work to lanes (subagents or parallel sessions), and services their output. Lanes never talk to the maintainer directly; they talk to the board and their artifacts. There is never a second gateway.

## Rationale

Multi-agent work needs a single point where intent enters and rulings exit, or the maintainer becomes a message bus between sessions that each hold partial context. The gateway holds the conversation-level context that cannot be serialized (what the maintainer meant, what was vetoed and why) and converts it into artifacts lanes can execute against. Serializing all coordination through one writer also eliminates a whole class of race conditions: two sessions assigning the same ruling number, two lanes filing contradictory decisions.

## What breaks without it

With two gateways, numbered rulings collide, and the maintainer answers the same question twice with drifting answers. With no gateway (maintainer talks to every lane), intake quality collapses to whichever lane asked, and no single place knows the whole state. Field observation: a decision-number collision between two concurrent sessions is what forced the single-writer rule in the source repo.
