# Skill: branch-commit-pattern

## Purpose

Apply canonical branch and commit naming from parent or sub-issue context.

## Rules

1. Parent issue branch:
   - `feat/REPO-XXXXX`
2. Sub-issue branch:
   - `feat/REPO-XXXXX__SUB-YY`
3. Commit message patterns:
   - parent issue commits: `type(IXX): message`
   - sub-issue commits: `type(IXX_SYY): message`

## Output Contract

- `branch_name`
- `commit_pattern`
- `context_type`: `parent` or `sub-issue`
