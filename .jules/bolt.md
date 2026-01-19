## 2024-05-23 - Caching pip in Composite Actions without Lockfiles
**Learning:** GitHub Composite Actions don't support `setup-python`'s built-in `cache: pip` without a dependency file. To cache tools installed via CLI (like `auto-code-rover`), we must manually use `actions/cache` with a key that includes `github.run_id` (to force updates) and `restore-keys` (to retrieve the latest cache).
**Action:** Always implement manual `actions/cache` with a rolling key strategy for CLI tool installations in Composite Actions.
