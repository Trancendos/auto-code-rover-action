## 2024-05-22 - [Critical Command Injection in GitHub Actions]
**Vulnerability:** Command Injection via unvalidated input in `action.yml`
**Learning:** Directly interpolating `${{ inputs.variable }}` into a `run` script allows command injection because the script is generated before execution.
**Prevention:** Always map inputs to environment variables and use the environment variables in the script (e.g., `env: VAR: ${{ inputs.var }}` and use `"$VAR"`).
