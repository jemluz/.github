# Skill: pr-create

## Purpose

Create PR metadata aligned with workflow rules for parent and sub-issue flows.

## Rules

1. PR base:
   - parent issue PR base: `dev`
   - sub-issue PR base: `feat/REPO-XXXXX`
2. PR title patterns:
   - parent: `[REPO-XXXXX] Title (PR #ZZ)`
   - sub-issue: `[REPO-XXXXX][SUB-YY] Title (PR #ZZ)`
3. PR body opening line must start with repository issue reference convention:
   - parent: `more details at issue #XX`
   - sub-issue: `more details at sub-issue #YY`
4. Milestone policy on PR:
   - parent PR may include milestone;
   - sub-issue PR must not include milestone.

## Output Contract

- `pr_base`
- `pr_title`
- `pr_body_first_line`
- `milestone_allowed`
