---
name: issue-to-implementation-plan
description: Use when the user asks to analyze a GitHub issue and convert it into an actionable implementation plan with explicit scope, phased tasks, risks, and validation criteria.
---

# Issue to Implementation Plan

Convert a GitHub issue into a clear, execution-ready implementation plan.

## When to use

Use this skill when work starts from an issue statement and the next needed output is a practical delivery plan (not code changes yet).

## Output contract (required)

Always return the plan using the exact section order below:

## Problem summary

- Summarize the issue in 2-5 bullets.
- Capture intent, expected outcome, and key constraints.

## Assumptions and open questions

- List assumptions required to proceed.
- List unanswered questions that can change implementation decisions.
- Mark each item clearly as `Assumption` or `Open question`.

## Scope

### In scope

- List what will be implemented now.

### Out of scope

- List what is explicitly excluded from this effort.

## Implementation phases with concrete tasks

- Break delivery into ordered phases.
- For each phase, include:
  - Objective
  - Concrete tasks (specific file/module/component level where possible)
  - Dependencies or sequencing constraints
  - Expected deliverable/output

## Risks and mitigations

- List technical and process risks that can impact delivery.
- Pair each risk with a practical mitigation.

## Acceptance criteria

- Define measurable completion criteria.
- Keep criteria testable and unambiguous.

## Validation checklist

- Include only checks relevant to this issue:
  - Tests to add/update/run
  - Build/type-check impact
  - Lint/format impact
  - Manual verification steps (if needed)
- If a category is not applicable, state `Not applicable` and why.

## Style requirements

- Be concise, explicit, and execution-focused.
- Prefer checklists and ordered phases over long prose.
- Avoid vague tasks like "implement feature"; always specify tangible work items.
