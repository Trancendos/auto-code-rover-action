## 2024-05-21 - [GitHub Actions Log UX]
**Learning:** Collapsing verbose installation logs with `::group::` and providing a Markdown summary via `GITHUB_STEP_SUMMARY` significantly improves Developer Experience for composite actions.
**Action:** Always wrap `pip install` or `npm install` steps in groups and check for output artifact existence before listing them in summaries.
