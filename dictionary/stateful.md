<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Stateful

> Carries information forward from one step to the next; a session is stateful across turns even though the model underneath is not.

*§02 Sessions, Context Windows & Turns · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/stateful)*

A stateful system remembers. Within a [session](./session.md), your coding agent is stateful: what you said in turn one still shapes turn twenty, because the [harness](./harness.md) keeps the transcript and sends the accumulated history with every request. That statefulness is manufactured. The [model](./model.md) receives the whole history each time and reconstructs 'what we were doing' from scratch; it just does so reliably enough to feel like continuity.

Across sessions the default flips back to [stateless](./stateless.md). Making an agent stateful over days and weeks means adding a layer that writes things down and reads them back: project instruction files, a [memory system](./memory-system.md), notes it leaves for its future self. Where that layer is thin you get the familiar symptom of re-explaining your architecture every morning.

Statefulness has a cost as well as a benefit. Everything the session retains occupies the [context window](./context-window.md) and competes for the model's attention, so a session that remembers everything also gets slower and vaguer. The useful stance is selective: make the state that matters durable in files, and let the rest expire with the session.

## In the tools

- Claude Code: session state lives in the transcript on disk; `claude --resume` reopens it, while CLAUDE.md and auto-memory carry state between sessions.
- Claude Cowork: projects keep files and instructions attached across conversations, which is the same trick applied to everyday work.

## In conversation

> “I told it to use pnpm in the first message and it's still using pnpm twenty turns later. So it does remember?”
>
> “Within the session, yes, it's stateful. Open a new one tomorrow and that instruction is gone unless it's in your project file.”

**Related:** [AGENTS.md](./agents-md.md) · [Turn](./turn.md) · [Handoff](./handoff.md)

## Learn it in the school

- [Course 01 · CLAUDE.md and Project Memory](https://vibecodeschool.com/learn/cc-05-claude-md-and-memory)
- [Course 06 · Projects, Memory, and Context](https://vibecodeschool.com/learn/cw-10-projects-and-memory)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/stateful) · added 2026-09-12
