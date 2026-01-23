## 2026-01-17 - Command Injection in GitHub Actions
**Vulnerability:** `action.yml` interpolated user input (`inputs.bug_id`) directly into a shell command using `${{ ... }}` syntax. This allows attackers to inject arbitrary shell commands if they control the input.
**Learning:** GitHub Actions inputs are not automatically sanitized when used in `run` scripts. Direct interpolation is dangerous.
**Prevention:** Always map inputs to environment variables using the `env` context, and use those environment variables in the shell script.

## 2026-05-21 - Argument Injection in Shell Scripts
**Vulnerability:** Even when using environment variables (e.g., `cmd --arg "$VAR"`), if the variable content starts with a hyphen (e.g., `-` or `--`), the command parser may interpret it as a flag rather than a value.
**Learning:** Quoting variables prevents word splitting but does not prevent flag injection if the tool's parser is standard (like argparse).
**Prevention:** Use the assignment syntax `--arg="$VAR"` which explicitly binds the value to the argument, preventing ambiguity.
