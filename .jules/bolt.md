## 2026-01-23 - [Stale Cache Prevention without Lockfile]
**Learning:** Using a purely static cache key (e.g., `v1`) in GitHub Actions causes the cache to become immutable and stale, as `actions/cache` does not overwrite existing keys.
**Action:** When no lockfile is available for hashing, use a slowly rotating component in the key (e.g., `date +%Y-%m`) to ensure caches are refreshed periodically while maintaining hit rates.
