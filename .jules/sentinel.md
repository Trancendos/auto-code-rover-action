# Sentinel Journal

## 2024-10-14 - Command Injection in Composite Action
**Vulnerability:** The `bug_id` input in `action.yml` is directly interpolated into a shell command (`run: auto-code-rover repair --bug-id ${{ inputs.bug_id }}`).
**Learning:** In GitHub Actions composite steps, inputs are not automatically escaped when used in `run` blocks. This allows command injection if the input contains shell metacharacters.
**Prevention:** Always assign inputs to environment variables and use the environment variable in the `run` script (e.g., `run: command "$INPUT_VAR"`).
