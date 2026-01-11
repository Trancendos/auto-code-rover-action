## 2024-05-22 - Optimization Constraints
**Learning:** Performance optimization tasks must respect architectural boundaries. Replacing a broken PyPI install with a git checkout is considered a 'fix' or 'architectural change', not a pure optimization, and may be rejected if it introduces complexity or new dependencies without explicit approval.
**Action:** When a tool is broken/missing, flag it as a fix task rather than forcing it through a performance optimization task. For optimization, stick to version upgrades and configuration tweaks unless authorized to refactor.
