# Copilot Instructions - _project name_

This file uses router pattern. Don't change the file name or the folder structure.
Docs folder don't exist here.

## 🛠️ Setup

For details on how to set up the project, see [Project Setup](../docs/project-setup.md).

## Project Context

Understand the project context and the problem it solves. This will help you to understand the instructions and apply them correctly.

See the [project context](../docs/project-context.md) for more information.

## 🏗️ Tech Stack

See the [tech stack](../docs/tech-stack.md) for more information.

## 📁 Folder Structure

See the [folder structure](../docs/folder-structure.md) for more information.

## 🧭 Instructions Map (Single Source of Truth)

| Scope             | File                                                                                                                          | Purpose                                                    |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Copilot routing   | [copilot-instructions.md](./copilot-instructions.md)                                                                          | Main AI routing and repository conventions.                |
| Delivery workflow | [dev-workflow/dev-workflow.md](./dev-workflow/dev-workflow.md)                                                                | Canonical naming, branch, commit, PR, and milestone rules. |
| Pull requests     | [pull_request_template.md](./pull_request_template.md)                                                                        | PR body structure and expected checklist.                  |
| Issues            | [ISSUE_TEMPLATE/general.yml](./ISSUE_TEMPLATE/general.yml) / [ISSUE_TEMPLATE/bug_report.yml](./ISSUE_TEMPLATE/bug_report.yml) | Issue title conventions and required issue fields.         |

## Skills

Execution is deterministic and must follow this order:

`current-opened-check -> issue-create -> subissue-link -> branch-commit-pattern -> pr-create -> workflow-validate`

`current-opened-check` is mandatory and always runs before any issue creation decision.

| Order | Skill                   | File                                                                 | Rule                                                                                                                                                       |
| ----- | ----------------------- | -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | `current-opened-check`  | [skills/current-opened-check.md](./skills/current-opened-check.md)   | Mandatory. If existing related issue/sub-issue is selected, skip `issue-create`.                                                                           |
| 2     | `issue-create`          | [skills/issue-create.md](./skills/issue-create.md)                   | Run only when creating a new parent issue or sub-issue.                                                                                                    |
| 3     | `subissue-link`         | [skills/issue-create.md](./skills/issue-create.md)                   | For sub-issue only: link child to parent using native GitHub sub-issue API; if native link fails, fallback to parent checklist link and continue delivery. |
| 4     | `branch-commit-pattern` | [skills/branch-commit-pattern.md](./skills/branch-commit-pattern.md) | Apply branch and commit patterns from issue context.                                                                                                       |
| 5     | `pr-create`             | [skills/pr-create.md](./skills/pr-create.md)                         | Build PR base/title/body from parent vs sub-issue context.                                                                                                 |
| 6     | `workflow-validate`     | [skills/workflow-validate.md](./skills/workflow-validate.md)         | Final gate before merge and closure.                                                                                                                       |

## Sub-issue Policy (GitHub native)

Goal: when creating child work items, prefer native GitHub sub-issue relationship over plain body links/checklists.

Rules:

1. Parent issue: normal issue.
2. Child issue: always create as normal issue first.
3. After child creation, link child to parent using native sub-issue API.
4. If native link fails (feature unavailable/permission/API error), fallback to parent checklist link.
5. Never block delivery because native linking failed; fallback is mandatory.
6. Keep title convention:
   - Parent: `[REPO-XXXXX] Title`
   - Child: `[REPO-XXXXX][SUB-YY] Title`
