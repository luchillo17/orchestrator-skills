# Orchestrator skills

[![skills.sh](https://skills.sh/b/luchillo17/orchestrator-skills)](https://skills.sh/luchillo17/orchestrator-skills)

An orchestrator dispatches work to a named agent, keeps a project board, and shares a store outside the repo. These skills are the conductor. Domain playbooks stay in the repo they belong to.

## Install

```bash
npx skills add luchillo17/orchestrator-skills -g
```

`-g` installs them for every project. Omit it to install into the current project. To update, run `npx skills update`.

Then start a thread and invoke the `orchestrator` skill.

## Skills

User-invoked skills run when you name them. Model-invoked skills load when a skill or a kickoff message tells the agent to follow them.

### User-invoked

- **[orchestrator](./skills/orchestrator/SKILL.md)**: Coordinate. A one-step answer stays in the chat. Otherwise name one agent by the subject, reply, then launch. Resume only for a follow-up on the same checkout.

### Model-invoked

- **[workspace-agent](./skills/workspace-agent/SKILL.md)**: Do the kickoff in a worktree. The orchestrator's kickoff names it, so the new agent loads it. The orchestrator moves the board.
- **[workspace](./skills/workspace/SKILL.md)**: The shared store, a sibling of the main checkout named `<folder>.workspace`. The chat gets the result. The board gets status. `docs/` gets a long artifact. `internal/` gets an agent note.
- **[project-board](./skills/project-board/SKILL.md)**: `notes.md` with For Review, In Progress, Queued, Done, and Canceled.
- **[delegate-work](./skills/delegate-work/SKILL.md)**: Kickoff template for a harness that cannot start a top-level agent. One PR per leaf task.
