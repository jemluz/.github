# Skill: issue-create

## Purpose

Create a new parent issue or sub-issue only when `current-opened-check` does not reuse an existing one.

## Rules

1. Enforce title patterns from workflow/templates:
   - Parent: `[REPO-XXXXX] Title`
   - Sub-issue: `[REPO-XXXXX][SUB-YY] Title`
   - Bug template variant: `[BUG][REPO-<ISSUE_NUMBER>] Bug Report title`
2. Respect parent vs sub-issue intent:
   - parent issue for new milestone feature slice;
   - sub-issue when scoped under existing parent issue.
3. Milestone policy:
   - set milestone for parent issue;
   - never set milestone for sub-issue.

## Output Contract

- `issue_type`: `parent` or `sub-issue`
- `issue_number`
- `issue_title`
- `parent_issue_number` (required for sub-issue)
- `milestone_applied`: `true` (parent) or `false` (sub-issue)
