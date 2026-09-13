<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Clearing

> Wiping the session so the next request starts from an empty context window, keeping only the standing instructions.

*§05 Handoffs · also called: /clear, Fresh session, Starting over · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/clearing)*

Clearing throws away the current [session](./session.md)'s conversation so the next request starts from an empty [context window](./context-window.md). Only the standing pieces survive: the [system prompt](./system-prompt.md), your [AGENTS.md](./agents-md.md) file, and whatever the [memory system](./memory-system.md) loads on startup. Everything else, including every file the [agent](./agent.md) read and every decision it made along the way, is gone. In Claude Code the command is `/clear`; other harnesses call it a new chat or a fresh thread.

Clearing feels like losing work, so people avoid it and push a bloated session onward instead. That is usually the wrong trade. Nothing you cleared was saved anywhere except in the window, so if a fact matters it should already live in a file, a commit, or a note. What a long session mostly holds is stale tool output and abandoned dead ends, and dragging those along is what pushes the agent out of the [smart zone](./smart-zone.md).

Clear at task boundaries, not mid-task. Finish the piece of work, commit it, write down anything the next session needs, then clear and start the next piece with a clean window. If the task is too big to finish before quality drops, that is a cue to write a [handoff](./handoff.md) rather than to push through. Prefer clearing over [compaction](./compaction.md) whenever the summary would need to carry more than a couple of sentences.

## In the tools

- Claude Code: `/clear` empties the conversation; CLAUDE.md and memory files are read again on the next turn.
- Codex: starting a new thread in the app, or a new `codex` run in the terminal, is the same move.
- Cursor: open a new chat instead of continuing the old one; rules files still apply.

## In conversation

> “It just rewrote the helper I told it not to touch, three times now.”
>
> “You've been in that session since lunch. Commit what's good, clear, and start the next piece with a fresh window.”
>
> “And re-explain everything?”
>
> “Only the two lines that matter. Everything else it can read from the repo.”

**Related:** [Checkpoint](./checkpoint.md) · [Attention degradation](./attention-degradation.md) · [Context engineering](./context-engineering.md)

## Learn it in the school

- [Course 01 · When to Interrupt vs Let It Run](https://vibecodeschool.com/learn/cc-20-when-to-interrupt)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/clearing) · added 2026-09-12
