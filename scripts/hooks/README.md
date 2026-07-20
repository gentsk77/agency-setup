# Git hooks: PR-only trunk (D7)

These hooks enforce D7 (no direct commits or pushes to `main`) on the client side.
They are tracked so every clone can enable them, but git does not activate a tracked
hooks directory automatically. Enable once per clone:

```
git config core.hooksPath scripts/hooks
```

- `pre-commit` rejects a commit made while `main`/`master` is checked out.
- `pre-push` rejects a push whose destination ref is `main`/`master`.

Both print a genuine-emergency override (`--no-verify`). This is client-side
enforcement: it binds this machine and is bypassable on purpose. Server-side
enforcement (GitHub branch protection or a ruleset) is stronger but needs the repo
to be public or on a paid plan; see D7 and STATE for that open call.
