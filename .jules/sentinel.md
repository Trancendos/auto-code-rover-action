## 2024-05-22 - Command Injection in Composite Action
**Vulnerability:** The `bug_id` input was directly interpolated into the shell command in `action.yml`, allowing for potential command injection if a malicious ID was provided.
**Learning:** GitHub Composite Actions (and workflows) often tempt developers to use `${{ inputs.x }}` directly in shell scripts, but this is unsafe for untrusted input.
**Prevention:** Map inputs to environment variables using the `env` block and reference them as shell variables (e.g., `"$BUG_ID"`) to ensure proper quoting and prevent code execution.
