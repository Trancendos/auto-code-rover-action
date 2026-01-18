## 2024-05-22 - Pip Caching in Composite Actions
**Learning:** In GitHub Composite Actions, `actions/setup-python`'s built-in caching requires a dependency file in the caller's repository. When installing tools via `pip` directly (no lockfile), use `actions/cache` manually.
**Action:** Use a cache key combining `runner.os` and `github.run_id` with `restore-keys` falling back to `runner.os` to ensure the cache updates (saves) on every run while restoring the previous run's cache.
