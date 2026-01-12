## 2024-05-23 - GitHub Actions Command Injection
**Vulnerability:** Unsanitized user input (`${{ inputs.bug_id }}`) directly interpolated into a shell command in `action.yml`.
**Learning:** GitHub Actions composite steps sharing inputs directly in `run` scripts are vulnerable to command injection if the input contains shell metacharacters.
**Prevention:** Always map inputs to environment variables and access them via `$ENV_VAR` in the shell script.
