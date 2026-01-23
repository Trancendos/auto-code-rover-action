## 2024-05-23 - Dynamic Dependency Caching
**Learning:** `actions/setup-python` cannot cache dependencies from a dynamically cloned repository (since `requirements.txt` doesn't exist at workflow start).
**Action:** Use `actions/cache` explicitly after the clone step, or check in a copy of `requirements.txt` to the action repo if possible. In this case, `actions/cache` is used as a step in the composite action.

## 2024-05-23 - No Setup File
**Learning:** `auto-code-rover` repository lacks `setup.py` or `pyproject.toml`, so `pip install .` fails.
**Action:** Must invoke `python app/main.py` directly. To make it less brittle, ensure `PYTHONPATH` is set correctly and use a pinned commit to avoid directory structure changes breaking the action.

## 2024-05-23 - Checkout vs Manual Git
**Learning:** Using `actions/checkout` with `ref` and `path` is safer and more standard than manual `git clone` commands, as it handles cleaning, existing directories, and fetching correctly across different runners.
**Action:** Always prefer `actions/checkout` for cloning external repositories in actions.
