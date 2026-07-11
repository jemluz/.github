# Skill: workflow-validate

## Purpose

Run final rule validation before merge/closure.

## Validation Gates

1. Branch naming matches parent/sub-issue pattern.
2. PR base branch matches context (`dev` for parent, parent branch for sub-issue).
3. Commit messages match allowed format:
    - `type(IXX): message`
    - `type(IXX_SYY): message`
4. PR title includes required `(PR #ZZ)` suffix and correct prefix pattern.
5. PR body starts with correct issue reference (`more details at issue #__`).
6. Issue/PR linkage points to the correct issue or sub-issue.
7. Milestone policy is respected (only parent issue and parent PR).
8. Merge rule is squash-only.

## Output Contract

- `status`: `pass` or `fail`
- `failed_rules`: list of violated checks
- `fix_actions`: concise corrective actions
