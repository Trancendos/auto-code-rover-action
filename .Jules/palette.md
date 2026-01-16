## 2024-03-21 - [GitHub Action Log UX]
**Learning:** In Composite Actions, users often overlook raw file listings in logs. Collapsing verbose setup logs with `::group::` and moving results to `$GITHUB_STEP_SUMMARY` drastically improves the "at-a-glance" experience.
**Action:** Always wrap setup steps in groups and use Summary for final artifacts in future Action improvements.
