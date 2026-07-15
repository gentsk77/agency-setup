# Profiles

Presets over the component registry: a named starting set plus the follow-up questions that tune it. The interview (SETUP.md Q2) recommends one; the maintainer can override or mix. A profile is a starting point, never a contract; the final set is whatever the interview settles.

| Profile | Components | For |
|---|---|---|
| `full-dev` | memory-core, claude-md-skeleton, gateway, dev-lanes, review-law, steward, ci-gates (+ design-lane if visual) | Projects that ship code seriously |
| `docs-research` | memory-core, claude-md-skeleton, gateway, steward | Writing, research, thinking repos |
| `eval-pipeline` | memory-core, claude-md-skeleton, gateway, gradable-rules (+ ci-gates if remote) | Screening candidates against criteria |
| `minimal` | memory-core, claude-md-skeleton | Throwaway or tiny repos |

Upgrading between profiles later is just installing the missing components (SETUP.md step 3 for the new set only); nothing about a smaller profile blocks growth.
