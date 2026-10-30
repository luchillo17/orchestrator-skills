---
name: delegate-work
description: Hand off a task when this harness has no native workers. Use when the orchestrator says to follow the delegate-work skill.
---

# Delegate work

Use this when the harness cannot start a top-level agent. The kickoff has a goal, a done-when, the files to touch, the files to leave, the quality bar, and where the result goes.

One PR per leaf task. Trust the report unless it is incomplete.

Done when the kickoff has those six parts and the leaf task has its own PR.
