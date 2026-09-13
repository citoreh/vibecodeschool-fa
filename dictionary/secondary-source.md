<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Secondary source

> An account of the thing rather than the thing itself: a summary, a paraphrase, a compaction. Useful, but one step removed from the truth.

*§05 Handoffs · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/secondary-source)*

A secondary source is a description of something rather than the something itself. A [handoff artifact](./handoff-artifact.md), a [compaction](./compaction.md) summary, a comment on a [ticket](./ticket.md), your own explanation of how the code works, or the [agent](./agent.md)'s recollection from earlier in the [session](./session.md) all count. Each one was accurate at some moment, through someone's eyes, at some level of detail. None of them is the code.

The problem is not that secondary sources are wrong, it is that they are quietly incomplete. A summary keeps what seemed important when it was written. If the task changes, the missing detail is often exactly what you now need, and nothing in the summary signals that it was dropped. Agents treat a clean summary with the same confidence as a file they just read, so the error stays invisible until something breaks.

Use secondary sources for orientation and [primary sources](./primary-source.md) for decisions. A handoff note is a good map of where to look; it is a poor substitute for looking. Before the agent changes code based on a summary, have it open the files the summary describes. When you write a handoff yourself, include paths and commands so the next reader can go straight to the source.

## In the tools

- Claude Code: the summary left behind by `/compact` is a secondary source; ask it to re-read key files after compacting.
- Most tools: earlier turns in a chat count too, since the model is reading its own past output, not the current state.

## In conversation

> “The handoff said the auth middleware was already migrated, so I had it build on that.”
>
> “Was it? The handoff is a secondary source. Did anyone check the file?”
>
> “No. Half of it is still on the old API.”
>
> “There it is. Orient with the note, decide from the code.”

**Related:** [Autocompact](./autocompact.md) · [Hallucination](./hallucination.md) · [Contextual knowledge](./contextual-knowledge.md)

## Learn it in the school

- [Course 05 · Long-Context Prompting](https://vibecodeschool.com/learn/pe-20-long-context-prompting)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/secondary-source) · added 2026-09-12
