# Bolt's Journal

## 2024-05-22 - [Initial Setup]
**Learning:** Initialized Bolt's journal for tracking performance insights.
**Action:** Always check this journal before starting optimizations.

## 2024-05-22 - [Composite Action Caching]
**Learning:** `actions/setup-python` built-in caching is ineffective in composite actions when the dependency file is missing in the user's repo.
**Action:** Use manual `actions/cache` with a dynamic key (`github.run_id`) and `restore-keys` to ensure caching works for internal dependencies.
