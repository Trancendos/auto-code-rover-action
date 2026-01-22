## 2026-01-17 - Command Injection in GitHub Actions
**Vulnerability:** `action.yml` interpolated user input (`inputs.bug_id`) directly into a shell command using `${{ ... }}` syntax. This allows attackers to inject arbitrary shell commands if they control the input.
**Learning:** GitHub Actions inputs are not automatically sanitized when used in `run` scripts. Direct interpolation is dangerous.
**Prevention:** Always map inputs to environment variables using the `env` context, and use those environment variables in the shell script.

## 2026-01-20 - Option Injection via Unquoted Arguments
**Vulnerability:** CLI tools using argparse/getopt can misinterpret arguments starting with `-` as flags if passed as positional arguments or separated by space (e.g., `--arg "$VAL"` where `$VAL` is `-foo`).
**Learning:** Shell argument parsing combined with tool argument parsing can be tricky. Using `--arg="$VAL"` binds the value to the argument more tightly in many parsers.
**Prevention:** Prefer `--arg="$VAL"` syntax over `--arg "$VAL"` when invoking CLI tools with untrusted input in shell scripts.
