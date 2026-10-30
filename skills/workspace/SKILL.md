---
name: workspace
description: Shape of the shared project store, its path, and when a file earns a place there. Use when the orchestrator or workspace-agent skill says to follow the workspace skill, or when you read or write the store.
---

# Workspace

The store is one directory outside the repo. A worktree uses the same path as the main checkout. The chat gets the result. The board gets status. `docs/` gets the long artifact.

## Root

From the project checkout or any of its worktrees, resolve the main checkout with `git rev-parse --path-format=absolute --git-common-dir`, then take that directory's parent. The store root is the sibling named `<folder>.workspace`, where `<folder>` is the main checkout's name. Create it if it is missing.

Done when you have that absolute path and the directory exists.

## Shape

- `notes.md` is the board. Follow the project-board skill.
- `docs/` is for a file a person opens.
- `internal/` is for an agent note.
- `preferences.md` is a short dated index of preferences for this project.

A preference that applies to every project goes in the user store, and only after the user agrees. Follow [HTML-PAGE.md](HTML-PAGE.md) when a file in `docs/` is a picture a sentence cannot carry. Markdown is the default.

Repo edits stay in the agent's worktree.

## When a file is worth writing

A file is worth writing when a later agent needs it without this chat.

- **internal/** One durable fact that changes how later work reads. The filename is the fact.
- **docs/** The long artifact of a real task. Link an artifact that already has a home. Do not copy it.
- **Brief.** A stored contract only for a task a later agent would repeat. The running contract is the kickoff message. A probe, a timer, or a steer gets no file.

Correct a stored contract only before its agent reads it. After that, send the correction to the agent and leave the file as it was.

## Examples

1. **Empty submodule.** A dead-code scan in a fresh worktree reports zero under `reference/`, because the submodule is empty there. The agent writes `internal/reference-submodule-empty.md`, and the result links it. Later scans read the note before they call zero clean.
2. **Report with a home.** An architecture pass writes its full report to the temp directory. The result names the top recommendation, lists each candidate with its strength, and links the file. There is no second copy. The board row points at that file.
3. **In-flight task.** The board row stays In Progress while its agent runs. A stored contract remains only if a later agent would run the same task again.
4. **Probe.** A "wait one minute" dispatch is a kickoff. No board row. No file. The agent reports in the thread.
5. **Correction after start.** The user changes 60 seconds to 30, then back, after the agent is running. The orchestrator steers the agent. The stored files stay as they were.
