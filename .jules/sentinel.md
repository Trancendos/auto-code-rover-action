## 2024-05-22 - GitHub Actions Command Injection
**Vulnerability:** Direct interpolation of `${{ inputs.bug_id }}` in `run` script allows command injection.
**Learning:** GitHub Actions `run` scripts are executed by the shell. Unsanitized inputs can break out of the command.
**Prevention:** Use environment variables to pass inputs to `run` scripts.
