## 2026-01-17 - Command Injection in GitHub Actions
**Vulnerability:** `action.yml` interpolated user input (`inputs.bug_id`) directly into a shell command using `${{ ... }}` syntax. This allows attackers to inject arbitrary shell commands if they control the input.
**Learning:** GitHub Actions inputs are not automatically sanitized when used in `run` scripts. Direct interpolation is dangerous.
**Prevention:** Always map inputs to environment variables using the `env` context, and use those environment variables in the shell script.
