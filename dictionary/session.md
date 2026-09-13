<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Session

> One continuous run with an agent, from an empty context to the moment you clear it, close it, or hand its work off.

*§02 Sessions, Context Windows & Turns · also called: Conversation, Thread · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/session)*

A session is a single stretch of work with an [agent](./agent.md), held together by one growing transcript. It begins with an empty [context window](./context-window.md) (apart from the [system prompt](./system-prompt.md) and any project files the [harness](./harness.md) loads), accumulates every [turn](./turn.md) you and the agent take, and ends when you clear it, close it, or it gets folded into a fresh one by [compaction](./compaction.md). Everything inside a session is visible to the model; everything outside it is not.

Sessions have a shape. Early on the agent is sharp, with a small context and clear instructions. As the transcript grows with file reads, test output and half-abandoned plans, the same model gets vaguer and starts contradicting itself. The cheapest fix for many 'it got worse' moments is not a better prompt but a new session with a tight brief.

So plan sessions as units of work. One task per session where you can; a clean [handoff](./handoff.md) between sessions when a task is bigger than one; and a written record of anything the next session must know, because the transcript itself will not follow you. Resuming an old session is handy for picking up exactly where you stopped, but it picks up all of the clutter too.

## In the tools

- Claude Code: `/clear` starts a new session in place; `claude --continue` and `claude --resume` reopen earlier ones from disk.
- Codex: each cloud task runs as its own session in an isolated container; the CLI keeps a local transcript per run.

## In conversation

> “Should I keep this session going for the API work too, or start over?”
>
> “Start over. You've been in this session for three hours and it's mostly test output now. Write the plan to a file and open a fresh one.”

**Related:** [Stateful](./stateful.md) · [Smart zone](./smart-zone.md) · [Clearing](./clearing.md)

## Learn it in the school

- [Course 01 · Your First Conversation](https://vibecodeschool.com/learn/cc-03-first-conversation)
- [Course 01 · When to Interrupt vs Let It Run](https://vibecodeschool.com/learn/cc-20-when-to-interrupt)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/session) · added 2026-09-12
