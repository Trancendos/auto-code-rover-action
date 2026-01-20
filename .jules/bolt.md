## 2025-01-01 - Optimizing Broken Actions
**Learning:** When an action relies on a package that doesn't exist (or isn't on PyPI), the "optimization" becomes "making it work efficiently".
**Action:** Always check if the package exists before assuming standard pip install works. For heavy dependencies like `torch`, caching is not just an optimization, it's a necessity for usability.
