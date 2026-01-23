## 2026-01-17 - Command Injection in GitHub Actions
**Vulnerability:** `action.yml` interpolated user input (`inputs.bug_id`) directly into a shell command using `${{ ... }}` syntax. This allows attackers to inject arbitrary shell commands if they control the input.
**Learning:** GitHub Actions inputs are not automatically sanitized when used in `run` scripts. Direct interpolation is dangerous.
**Prevention:** Always map inputs to environment variables using the `env` context, and use those environment variables in the shell script.

## 2026-01-17 - Deprecated GitHub Action Runtimes
**Vulnerability:** Usage of `actions/setup-python@v2` forces the use of the deprecated Node 12 runtime, which is no longer supported and may have unpatched vulnerabilities.
**Learning:** GitHub Actions evolve their runtime environment (Node.js). Action versions must be kept up-to-date to run on supported infrastructure (e.g., Node 20).
**Prevention:** Regularly audit `uses` directives in `action.yml` and workflows to ensure they point to versions using currently supported Node.js LTS releases (e.g., `setup-python@v5`, `checkout@v4`).
