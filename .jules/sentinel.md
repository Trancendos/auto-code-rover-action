## 2026-01-17 - Command Injection in GitHub Actions
**Vulnerability:** `action.yml` interpolated user input (`inputs.bug_id`) directly into a shell command using `${{ ... }}` syntax. This allows attackers to inject arbitrary shell commands if they control the input.
**Learning:** GitHub Actions inputs are not automatically sanitized when used in `run` scripts. Direct interpolation is dangerous.
**Prevention:** Always map inputs to environment variables using the `env` context, and use those environment variables in the shell script.

## 2026-01-21 - Argument Injection in Shell Scripts
**Vulnerability:** Passing arguments as `--arg "$VAR"` in shell scripts can lead to argument injection if `$VAR` starts with `-`. The receiving program might interpret it as a flag.
**Learning:** Even with environment variables, the way arguments are passed matters for robustness.
**Prevention:** Use `--arg="$VAR"` syntax to explicitly bind the value to the argument, ensuring it is treated as a value even if it starts with a hyphen.
