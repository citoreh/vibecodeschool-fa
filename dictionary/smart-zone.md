<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Smart zone

> The early stretch of a session where the agent is at its sharpest; past it, the same model gets sloppier and forgetful.

*§04 Failure Modes · also called: Dumb zone, Smart zone / dumb zone · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/smart-zone)*

The smart zone is the part of a [session](./session.md) where the [agent](./agent.md) does its best work: [context](./context.md) is small and relevant, instructions are fresh, and the [model](./model.md) can hold the whole task in view. Everyone who uses coding agents has felt the other side of it, the dumb zone, where a session that has run for hours starts making mistakes it would never have made in its first ten minutes. The model did not change. The context did, and [attention degradation](./attention-degradation.md) did the rest.

Where the line falls depends on the model and on what is in the window, and it is fuzzy rather than sharp, but it usually arrives well before the [context window](./context-window.md) is full. Plenty of free window is no guarantee; quality can be gone long before capacity is. The signs are behavioural: repeated corrections, drifting from the plan, confident claims about files it read a long time ago.

Treat the zone as the resource you are spending, not the token count. Start a task in a fresh session so it lands in the sharp part; when a job clearly exceeds one session's good stretch, break it at a natural seam and [hand off](./handoff.md) with a written plan. The tempting shortcut, adding a second job to a session because it 'already has the context', is exactly what pushes the second job into the dumb zone.

## In the tools

- Claude Code: `/clear` between tasks is the cheapest way to stay in the smart zone; `/compact` with a focus note keeps a long task inside it.
- Codex: cloud tasks start each job in a fresh container and session, which keeps every task in its own smart zone by construction.

## In conversation

> “Is there a point where I should just stop and start a new session?”
>
> “When it starts needing the same correction twice. That's the dumb zone. You'll get more from a fresh session than from a fifth explanation.”

**Related:** [Attention budget](./attention-budget.md) · [Clearing](./clearing.md) · [Compaction](./compaction.md) · [Turn](./turn.md)

## Learn it in the school

- [Course 01 · When to Interrupt vs Let It Run](https://vibecodeschool.com/learn/cc-20-when-to-interrupt)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/smart-zone) · added 2026-09-12
