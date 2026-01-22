## 2025-01-22 - Caching in Composite Actions without Lockfiles
**Learning:** GitHub Composite Actions running in the caller's context cannot rely on `actions/setup-python`'s built-in caching if the dependencies are installed via command line (not file). Manual `actions/cache` is required.
**Action:** Use `actions/cache` with a static key (e.g., `${{ runner.os }}-pip-v1`) and `restore-keys` for dependency caching in composite actions lacking repository-hosted dependency files. Avoid using `${{ github.run_id }}` in cache keys to prevent cache explosion.
