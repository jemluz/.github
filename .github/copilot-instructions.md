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

| Scope | File | Purpose |
| --- | --- | --- |
| Copilot routing | [copilot-instructions.md](./copilot-instructions.md) | Main AI routing and repository conventions. |
| Delivery workflow | [dev-workflow/dev-workflow.md](./dev-workflow/dev-workflow.md) | Canonical naming, branch, commit, PR, and milestone rules. |
| Pull requests | [pull_request_template.md](./pull_request_template.md) | PR body structure and expected checklist. |
| Issues | [ISSUE_TEMPLATE/general.yml](./ISSUE_TEMPLATE/general.yml) / [ISSUE_TEMPLATE/bug_report.yml](./ISSUE_TEMPLATE/bug_report.yml) | Issue title conventions and required issue fields. |

## Skills

Execution is deterministic and must follow this order:

`current-opened-check -> issue-create -> branch-commit-pattern -> pr-create -> workflow-validate`

`current-opened-check` is mandatory and always runs before any issue creation decision.

| Order | Skill | File | Rule |
| --- | --- | --- | --- |
| 1 | `current-opened-check` | [skills/current-opened-check.md](./skills/current-opened-check.md) | Mandatory. If existing related issue/sub-issue is selected, skip `issue-create`. |
| 2 | `issue-create` | [skills/issue-create.md](./skills/issue-create.md) | Run only when creating a new parent issue or sub-issue. |
| 3 | `branch-commit-pattern` | [skills/branch-commit-pattern.md](./skills/branch-commit-pattern.md) | Apply branch and commit patterns from issue context. |
| 4 | `pr-create` | [skills/pr-create.md](./skills/pr-create.md) | Build PR base/title/body from parent vs sub-issue context. |
| 5 | `workflow-validate` | [skills/workflow-validate.md](./skills/workflow-validate.md) | Final gate before merge and closure. |
