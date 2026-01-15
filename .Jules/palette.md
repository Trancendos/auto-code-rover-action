## 2026-01-15 - [GitHub Action Summary]
**Learning:** GitHub Actions logs can be overwhelming. Users often miss important artifacts buried in logs.
**Action:** Always use `::group::` for setup steps and `$GITHUB_STEP_SUMMARY` to surface critical outputs (like repair results) directly in the UI.
