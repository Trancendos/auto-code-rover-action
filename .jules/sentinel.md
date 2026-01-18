## 2026-01-16 - Command Injection in GitHub Actions
**Vulnerability:** Unsafe interpolation of user input `${{ inputs.bug_id }}` directly into a shell command in `action.yml`.
**Learning:** GitHub Actions inputs are not automatically sanitized when used in `run` steps. Direct interpolation allows attackers to inject shell commands.
**Prevention:** Always map inputs to environment variables and use the environment variable in the shell command (e.g., `env: INPUT: ${{ inputs.x }}` and use `"$INPUT"`).
