## 2024-05-23 - [GitHub Actions Command Injection]
**Vulnerability:** Command injection risk in `action.yml`. The input `bug_id` was interpolated directly into a shell command using `${{ inputs.bug_id }}`.
**Learning:** GitHub Composite Actions running bash scripts are vulnerable to command injection if inputs are not sanitized or isolated. Using `env` context is the standard way to mitigate this.
**Prevention:** Always map inputs to environment variables in the `env` block and use the environment variable in the `run` script.
