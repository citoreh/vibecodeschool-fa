<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Handoff

> Ending one session and starting another on the same task, carrying the state forward in writing rather than in the window.

*§05 Handoffs · also called: Hand-off, Session handoff · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/handoff)*

A handoff moves a task from one [session](./session.md) to the next without losing the plot. The old session ends, whether by [clearing](./clearing.md), [compaction](./compaction.md), or simply closing the terminal, and a new one picks the work up. Since the model is [stateless](./stateless.md) between sessions, nothing crosses that gap on its own. Anything the next session should know must be written down where it will look: a file in the repo, a commit message, a note on the [ticket](./ticket.md).

The failure looks like déjà vu. The new session re-investigates the codebase, rediscovers the constraint you settled an hour ago, and sometimes decides differently. Or it confidently continues from a summary that dropped the one detail that mattered, such as the reason you rejected the obvious approach. A handoff that lives only in your head is not a handoff.

Do it on purpose. Before you leave a session, ask the [agent](./agent.md) to write a [handoff artifact](./handoff-artifact.md): what was done, what remains, what was decided and why, and which files to read first. Keep it grounded in [primary sources](./primary-source.md) like the actual diff and the test output, not the agent's memory of them. The next session starts by reading that note, checks it against the repo, and only then begins.

## In the tools

- Claude Code: ask for a HANDOFF.md before you `/clear`, or use `/compact` with instructions about what to keep.
- Antigravity: task lists and walkthroughs are artifacts the next run can read instead of the chat.
- Codex: a cloud task ends in a pull request, which is itself a handoff back to you.

## In conversation

> “I'm out of context and the migration is half done. Do I just keep going?”
>
> “No. Have it write a handoff: what's done, what's left, and the decisions. Commit it. Then clear and read it in.”
>
> “Feels like overhead.”
>
> “Ten minutes of overhead beats an hour of the next session re-learning the schema.”

**Related:** [Spec](./spec.md) · [Checkpoint](./checkpoint.md) · [Smart zone](./smart-zone.md)

## Learn it in the school

- [Course 03 · Plans and Task Lists](https://vibecodeschool.com/learn/ag-06-planner-agents)
- [Course 01 · Iterative Refinement](https://vibecodeschool.com/learn/cc-19-iterative-refinement)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/handoff) · added 2026-09-12
