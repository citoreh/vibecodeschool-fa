<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Steering

> Nudging a running agent back on course, mid-turn or between turns, before a wrong call becomes the foundation for everything after it.

*§02 Sessions, Context Windows & Turns · also called: Interrupting, Redirecting, Course-correcting · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/steering)*

Steering is the act of correcting an [agent](./agent.md) while the work is in flight. It can happen mid-[turn](./turn.md) (in Claude Code, pressing Escape stops the current action and lets you type; most harnesses let you queue a message while the agent is still working) or between turns, with a short instruction that changes direction: stop, use the existing helper instead, that's the wrong file. The agent keeps its [context](./context.md) and continues from the correction rather than from scratch.

Timing decides the cost. An agent that makes a bad call in minute one and is redirected in minute two loses a minute. The same bad call left alone becomes the assumption every later edit builds on, and by the time you notice, unwinding it means reverting a dozen files and re-explaining the goal. This is why watching the first few actions of a task closely, then relaxing, beats checking in evenly throughout.

Steer with the smallest correction that fully removes the ambiguity. Name the file, paste the error, restate the goal in one line; long explanations mid-task add context without adding clarity. When the transcript has accumulated several corrections and the agent is still drifting, steering has stopped paying: [clearing](./clearing.md) and restarting with a better brief, or a [handoff artifact](./handoff-artifact.md) that captures what you learned, is cheaper than a fourth nudge.

## In the tools

- Claude Code: Escape interrupts the current action; typing while it works queues your message for the next step; Escape twice opens `/rewind` to restore an earlier checkpoint if a correction comes too late.
- Antigravity: agents can be paused, redirected or cancelled from the manager view without losing their task history.
- Cursor: stopping a generation keeps the partial changes for you to accept or reject before continuing.

## In conversation

> “It's rewriting the whole auth module and I only asked for the logout bug.”
>
> “Hit Escape and steer it: 'Stop. Only touch `logout()`. Leave the rest.' Don't wait for it to finish the rewrite.”

**Related:** [Human-in-the-loop](./human-in-the-loop.md) · [Checkpoint](./checkpoint.md) · [Plan mode](./plan-mode.md)

## Learn it in the school

- [Course 01 · When to Interrupt vs Let It Run](https://vibecodeschool.com/learn/cc-20-when-to-interrupt)
- [Course 03 · Stopping, Steering, and Retrying](https://vibecodeschool.com/learn/ag-14-cancellation-retries)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/steering) · added 2026-09-12
