# Palette's UX Journal

## 2024-10-12 - GitHub Action DX Improvements
**Learning:** Users of GitHub Actions often rely on the Job Summary page for quick status checks rather than digging into raw logs. Providing a structured markdown summary significantly improves observability and reduces cognitive load.
**Action:** Implement `GITHUB_STEP_SUMMARY` for outputting results and use log grouping for setup steps in all future composite actions.

## 2024-10-27 - Immediate Visibility of Artifacts
**Learning:** For GitHub Actions that produce text-based artifacts (like patches or logs), displaying a collapsible preview in `GITHUB_STEP_SUMMARY` drastically improves the "time-to-insight" by removing the need to download artifacts.
**Action:** Always check if small, text-based output artifacts can be rendered directly in the job summary for composite actions.
