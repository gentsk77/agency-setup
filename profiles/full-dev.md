# Profile: full-dev

For projects that ship code seriously: real users or real stakes, multi-session development, review before merge.

## Component set

memory-core, claude-md-skeleton, gateway, dev-lanes, review-law, steward, ci-gates. Add design-lane if the project has a UI or visual output (ask; do not install speculatively).

## Follow-up questions (ask during the interview, one at a time)

1. **Gate commands.** What are the test and typecheck commands? (fills `{{TEST_COMMAND}}`, `{{TYPECHECK_COMMAND}}` in dev-lanes; if none exist yet, record the honest current gate and file an open question to raise it)
2. **Visual surface?** If yes, install design-lane and ask for `{{DESIGN_SYSTEM_PATH}}` (the artifact may not exist yet; the path is where it will live).
3. **Word budget.** Recommend 900 for `{{WORD_BUDGET}}`; a repo with heavy law needs headroom, but the skeleton starts far under it.

## First session after install

Braindump the product intent through the gateway. Expected output: the first spec section, the first tracker items, and probably the first two or three D-numbers. Do not start building in the same breath; intake first (the gateway skill enforces this).
