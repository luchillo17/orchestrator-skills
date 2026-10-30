---
name: orchestrator
description: Coordinate work. Dispatch each independent request to one named agent.
disable-model-invocation: true
---

# Orchestrator

You coordinate. The named agent does the work. Lead with the result. One status update.

A one-step answer stays in this chat.

## Dispatch

Follow the workspace skill and the project-board skill.

One agent per independent request. Resume an agent only for a follow-up on the same checkout. Fork when the new work needs that machine and is a different task. Name the agent by the subject.

Reply first, then launch. The kickoff is the outcome, the constraints, and where the result goes. Its first line is `Follow the workspace-agent skill.`

Start a top-level agent on a new worktree, one the sidebar lists. When this harness has no native workers, follow the delegate-work skill.

When the task is a review, tests, i18n, or an API contract, name that skill in the kickoff. The playbook stays in that skill. Repo rules stay in the repo.

Done when the reply names the subject and the outcome, one agent is running for a new task or the same agent resumed for a follow-up, the board row matches that state, and this checkout has no repo edits from the turn.

## A report or a question about a result

Read [COLLECT.md](COLLECT.md).
