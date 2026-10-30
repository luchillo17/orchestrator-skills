---
name: project-board
description: Keep the project board in notes.md, with For Review, In Progress, Queued, Done, and Canceled. Use when the orchestrator says to follow the project-board skill, or when you add or move a task.
---

# Project board

The board is `notes.md` in the workspace root from the workspace skill. Status lives here. The chat carries the result. A long artifact lives in `docs/`.

A probe, a timer, or a steer does not get a row.

## File

```markdown
---
format: project-board
description: <one sentence>
taskPrefix: <PREFIX>
---

## Tasks

## For Review

## In Progress

## Queued

## Done

## Canceled
```

Only these headings, in this order. The next id is one higher than the highest `<PREFIX>-N` already in the file. An id never changes and is never reused.

## Row

`- [ ] **PREFIX-N** Title [file:<path>] [pr:<number>] [agent:<subject>]`

Checked only under Done and Canceled. Chips stay in that order: one store file, one PR, one agent. Drop the agent chip when the row is Done or Canceled and a file or PR remains.

A parent with no file or agent of its own takes the status of its most active open child: In Progress, then For Review, then Queued. It moves to Done when every child is Done or Canceled.

Done when the row is under the heading that matches the work, the id is unchanged, and the chips match what still exists.
