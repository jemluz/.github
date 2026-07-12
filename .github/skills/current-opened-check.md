# Skill: current-opened-check

## Purpose

Find related open parent issues and sub-issues before creating a new one.

## Inputs

- Problem statement from user request.
- Open issues dataset (parent + sub-issue candidates).

## Parent/child discovery update

Search strategy must include:
1. Open parent issues.
2. Existing native sub-issues under candidate parents.
3. Existing checklist-linked children in parent body (fallback mode).

## Deterministic Steps

1. Search open parent issues and open sub-issues.
2. Use default matching strategy: semantic match on **title + body**.
3. Rank candidates by confidence (`high`, `medium`, `low`) with short reason.
4. If related candidates exist, prompt user:
   - reuse existing issue/sub-issue, or
   - create new issue.
5. If user selects an existing issue/sub-issue:
   - skip `issue-create`;
   - propagate selected issue context to next skills.
6. If user selects create new, continue to `issue-create`.

## Output Contract

- `match_status`: `related-found` or `no-related-found`
- `selected_issue_context`: existing issue/sub-issue metadata or `null`
- `next_skill`: `issue-create` or `branch-commit-pattern`
