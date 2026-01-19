## 2024-05-23 - [Pip Caching in GitHub Composite Actions]
**Learning:** In GitHub Composite Actions without a lockfile, `actions/setup-python`'s built-in caching cannot be used. Instead, use `actions/cache` with a key combining `runner.os` and `github.run_id`, and `restore-keys` falling back to `runner.os`. This ensures the cache is updated on every run (write-heavy) while still benefitting from previous runs.
**Action:** Use this pattern when optimizing composite actions that install dependencies via `pip install <package>` directly.
