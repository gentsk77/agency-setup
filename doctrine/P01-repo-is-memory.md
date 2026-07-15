# P01: The repo is the memory, not the conversation

## Statement

Everything a future session needs lives in the repository: orientation in a one-screen handoff note (STATE), history in an append-only journal, rulings in a numbered decision log, unknowns in a question queue. Conversation history is scratch space; when a session ends, anything durable it produced has been routed into a file.

## Rationale

Agent sessions are ephemeral and context windows are finite. Any fact that lives only in a conversation is lost the moment the session closes, and worse, half-remembered versions of it leak into later sessions as confident hallucination. Files are the only substrate that every future session (human or agent) reads the same way. The discipline also forces clarity: a thought that cannot be written into its home file was not actually settled.

## What breaks without it

Sessions re-litigate settled questions, contradict earlier rulings they never saw, and rebuild context by re-reading the whole repo instead of one screen. Handoffs between sessions degrade into archaeology. Field observation: repos without a handoff note spend the first quarter of every session reconstructing what the last one knew.
