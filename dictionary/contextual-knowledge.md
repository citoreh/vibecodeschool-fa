<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Contextual knowledge

> Facts the model has because they are in the context window right now, as opposed to facts it remembers from training.

*§04 Failure Modes · also called: In-context knowledge · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/contextual-knowledge)*

Contextual knowledge is what the [model](./model.md) knows from the current request: the files the [agent](./agent.md) has read, the docs you pasted, the error output, the instructions in your project file. It is the counterpart to [parametric knowledge](./parametric-knowledge.md). Anything in the [context window](./context-window.md) can override what the model would otherwise assume, which is the whole reason coding agents read files before editing them instead of writing from memory.

It is also the more reliable of the two, as long as it is actually there and still accurate. Models generally trust the context over their training when the two conflict, so a pasted changelog beats a stale habit. The failures come when people assume something is in context and it is not (the agent never opened that file), or when it was in context but has since changed on disk (you edited it after the read).

Make contextual knowledge deliberate. Point the agent at the specific files that define the truth for this task, refresh them after big changes, and prefer [primary sources](./primary-source.md) over your own summary of them. When an answer seems to ignore your codebase, ask what it read; the honest reply is often 'nothing yet'.

## In the tools

- Claude Code: `@path/to/file` loads a file into context explicitly; a Read tool call does the same thing on the agent's own initiative.
- Cursor: files open in the editor and anything attached via `@` are the request's contextual knowledge.

## In conversation

> “Why did it get the config right this time and wrong yesterday?”
>
> “Yesterday it worked from memory. Today you pasted the actual config, so it had contextual knowledge instead of a guess.”

**Related:** [Context](./context.md) · [Knowledge cutoff](./knowledge-cutoff.md) · [Context pointer](./context-pointer.md)

## Learn it in the school

- [Course 04 · RAG Fundamentals](https://vibecodeschool.com/learn/aa-07-rag-fundamentals)
- [Course 05 · RAG Prompting Patterns](https://vibecodeschool.com/learn/pe-21-rag-prompting-patterns)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/contextual-knowledge) · added 2026-09-12
