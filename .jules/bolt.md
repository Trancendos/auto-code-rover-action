## 2024-05-23 - [Pip Caching Strategy]
**Learning:** In GitHub Actions without a lockfile, standard caching strategies fail because there's no static file to hash.
**Action:** Use a "rolling cache" strategy: key includes `github.run_id` (always new) and `restore-keys` falls back to `runner.os` prefix. This ensures we always restore the latest cache and save a fresh one.
