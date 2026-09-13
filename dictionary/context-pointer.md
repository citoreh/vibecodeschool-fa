<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Context pointer

> A short reference that tells the agent where information lives and when to fetch it, instead of the information itself.

*§06 Memory & Steering · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/context-pointer)*

A context pointer is a one-line reference to information rather than the information: “the auth flow is described in docs/auth.md,” or “run `pnpm test:e2e` to see the browser tests.” It occupies a few [tokens](./token.md) in the [context window](./context-window.md) and tells the [agent](./agent.md) that a resource exists, where it is, and when it is relevant. When a task calls for it, the agent chases the pointer via a [tool call](./tool-call.md); otherwise it leaves it alone.

Pointers are the mechanism behind [progressive disclosure](./progressive-disclosure.md), and their absence is why instruction files bloat. Without a pointer, the only way to make sure the agent knows something is to paste it, so people paste. With a pointer, the knowledge costs almost nothing until it is used. The failure mode of pointers is vagueness: “see the docs” points nowhere, and the agent will not go looking.

Write pointers with a path, a trigger, and a reason. Path: the exact file, command, or URL. Trigger: the situation that should send the agent there. Reason: one clause on why it matters, so the agent can judge relevance. Keep them in [AGENTS.md](./agents-md.md) for project-wide facts and in [handoff notes](./handoff-artifact.md) for task-specific ones. The [primary source](./primary-source.md) stays where it is; only the pointer travels.

## In the tools

- Claude Code: `@path/to/file` in a prompt is a pointer the harness resolves immediately; a line in CLAUDE.md is one the agent resolves when relevant.
- Cursor: `@docs` references and rule descriptions act as pointers the agent expands on demand.

## In conversation

> “How do I get it to follow our migration checklist without pasting all forty steps?”
>
> “A context pointer. One line: 'Before any schema change, read docs/migrations.md and follow it.'”
>
> “And it'll actually open it?”
>
> “When a schema change comes up, yes. Until then it costs you one line.”

**Related:** [Context engineering](./context-engineering.md) · [Secondary source](./secondary-source.md) · [Skill](./skill.md)

## Learn it in the school

- [Course 01 · CLAUDE.md and Project Memory](https://vibecodeschool.com/learn/cc-05-claude-md-and-memory)
- [Course 01 · Searching the Codebase](https://vibecodeschool.com/learn/cc-07-searching-the-codebase)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/context-pointer) · added 2026-09-12
