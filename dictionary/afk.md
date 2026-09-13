<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# AFK

> Away from keyboard: you start the agent, leave, and come back to finished work you review later instead of supervising live.

*§07 Patterns of Work · also called: Away from keyboard, Unattended run, Fire and forget · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/afk)*

AFK is the pattern where you hand the [agent](./agent.md) a task and walk away. No approvals, no mid-run [steering](./steering.md); the agent runs to completion on its own and you read the result later. It needs a permissive [permission mode](./permission-mode.md) so nothing blocks waiting for a click, and usually a [sandbox](./sandbox.md) or a [worktree](./worktree.md) so a bad run can't damage anything that matters.

This is where the leverage of AI coding lives. One person can have several AFK runs going while doing something else, and the runs happen overnight or during meetings. The failure to watch for is quiet: the agent hits an ambiguity, picks an answer, and spends the next hour building tidy, internally consistent work on top of it. Nothing crashes. You only find out when you read the diff.

Make the run safe to leave. Do the thinking before you go: a [grilling](./grilling.md) pass and a written [spec](./spec.md) take the guesses off the table. Put [automated checks](./automated-check.md) in the loop so failing tests stop the run instead of you. And make the finish line a branch or a pull request you can read through, never a merge that already happened. AFK doesn't make [human review](./human-review.md) optional; it batches all of it into one sitting at the end, so what comes out of the run has to be worth reading.

## In the tools

- Claude Code: a permission mode that auto-accepts (or `--dangerously-skip-permissions`) inside the built-in sandbox; cloud sessions are AFK by design.
- Codex: cloud tasks run in an isolated container and come back as a diff or a pull request.
- Antigravity: the Agent Manager is built around unattended runs, with an inbox that collects anything needing a human.

## In conversation

> “The agent asked me two questions in the first ten minutes and then went quiet for an hour.”
>
> “That's the point of AFK. Answer those questions up front in the spec next time and you can leave the whole run alone.”
>
> “And if it goes off the rails?”
>
> “It's in a sandbox on its own branch. Worst case you delete the branch.”

**Related:** [Headless mode](./headless-mode.md) · [Human-in-the-loop](./human-in-the-loop.md) · [Handoff artifact](./handoff-artifact.md)

## Learn it in the school

- [Course 03 · The Inbox: Running Agents Without Watching Them](https://vibecodeschool.com/learn/ag-15-human-in-the-loop)
- [Course 06 · Cloud Sessions and Your Phone](https://vibecodeschool.com/learn/cw-13-cloud-sessions-and-mobile)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/afk) · added 2026-09-12
