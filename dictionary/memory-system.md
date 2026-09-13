<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Memory system

> Whatever lets an agent carry information across sessions: notes on disk, a memory directory, a store it reads at startup.

*§06 Memory & Steering · also called: Memory, Persistent memory, Auto-memory · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/memory-system)*

A memory system is any mechanism that lets an [agent](./agent.md) remember something after the [session](./session.md) ends. Since the [model](./model.md) is [stateless](./stateless.md) and the [context window](./context-window.md) is thrown away, remembering has to be built: the [harness](./harness.md) writes facts to files or a database during a session and loads them back into [context](./context.md) at the start of the next one. That is all memory is, at every scale, from a `MEMORY.md` to a vector store.

Two failure shapes. One, no memory at all: every session re-learns your conventions, your quirks, and the thing you told it yesterday. Two, memory that grows without curation, so each session starts with a wall of stale notes competing for [attention](./attention-budget.md). A memory that says the tests take five minutes when they now take thirty is worse than no memory, because it is trusted.

Keep memory small, factual, and dated. Store decisions and preferences, not transcripts. Put project-wide facts in [AGENTS.md](./agents-md.md) where every session sees them, and keep personal or volatile notes in a memory file the harness loads on demand. Review it occasionally the way you would a runbook. Anything the repo already records, such as code structure or history, does not belong in memory; the agent can read the [primary source](./primary-source.md).

## In the tools

- Claude Code: CLAUDE.md is shared project memory; a per-project auto-memory directory holds notes the agent writes for itself between sessions.
- Claude Cowork: projects keep files and instructions attached so each task starts with the same grounding.
- Cursor: rules files carry the durable instructions; saved memories from past chats can be layered on top.

## In conversation

> “Why does it keep suggesting npm when we're a pnpm repo?”
>
> “Because nothing tells it. Add one line to the memory file and it stops.”
>
> “Won't it forget again next session?”
>
> “That's the point of the memory system: it's loaded every time. Just keep it short.”

**Related:** [Context engineering](./context-engineering.md) · [Progressive disclosure](./progressive-disclosure.md) · [Handoff artifact](./handoff-artifact.md)

## Learn it in the school

- [Course 01 · CLAUDE.md and Project Memory](https://vibecodeschool.com/learn/cc-05-claude-md-and-memory)
- [Course 06 · Projects, Memory, and Context](https://vibecodeschool.com/learn/cw-10-projects-and-memory)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/memory-system) · added 2026-09-12
