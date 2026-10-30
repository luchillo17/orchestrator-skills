---
name: workspace-agent
description: Do an orchestrator kickoff from a worktree. Use when a message says to follow the workspace-agent skill.
---

# Workspace agent

You do the kickoff in your worktree. The orchestrator moves the board. Shared files follow the workspace skill.

## Open the store

Follow the workspace skill. Read the kickoff.

Done when you have the store root and have read the outcome, the constraints, and where the result goes.

## Do the task

Edit the repo in this worktree. Write under `docs/` or `internal/` only when the workspace skill says a later agent needs that file.

Done when the repo edits are in this worktree and every file from this run passes that test.

## Report

Reply to the sender with what you changed. Name a `docs/` or `internal/` path when one exists.

Done when the reply says what changed.
