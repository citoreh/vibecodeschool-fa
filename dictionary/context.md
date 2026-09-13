<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Context

> Everything the agent currently has in front of it that bears on the task: loaded files, your messages, tool results so far.

*§02 Sessions, Context Windows & Turns · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/context)*

Context is the information the agent is actually working from right now. Not what exists in your repo, not what the model absorbed in [training](./training.md), but the specific text that has been loaded into the current [session](./session.md): your instructions, the files it has read, the command output it has seen, the plan it wrote three [turns](./turn.md) ago. If a fact is not in the context, the agent is either guessing from [parametric knowledge](./parametric-knowledge.md) or inventing.

This is why two people can run the same prompt and get wildly different results. One pasted the failing test and the relevant module; the other typed 'fix the bug'. The model was identical; the context was not. Most 'the AI is dumb today' complaints turn out to be 'the agent never saw the thing I assumed it knew'.

Good context is relevant, current and small. Point the agent at the two files that matter instead of the whole directory; paste the actual error instead of describing it; drop stale plans once they are done. The container the context lives in is the [context window](./context-window.md), and it is finite, so every irrelevant line you load competes with the lines that matter. Managing this on purpose is the discipline of [context engineering](./context-engineering.md).

## In the tools

- Claude Code: `/context` shows what is occupying the window; `@file` mentions load a file into context deliberately.
- Cursor: the `@` menu attaches files, docs and web results to the request explicitly.

## In conversation

> “It keeps proposing a fix for a function that doesn't exist anymore.”
>
> “Check the context. It read that file before your refactor and hasn't looked since. Tell it to re-read the module.”

**Related:** [Contextual knowledge](./contextual-knowledge.md) · [Attention budget](./attention-budget.md) · [System prompt](./system-prompt.md)

## Learn it in the school

- [Course 04 · Context Engineering](https://vibecodeschool.com/learn/aa-06-context-engineering)
- [Course 05 · Long-Context Prompting](https://vibecodeschool.com/learn/pe-20-long-context-prompting)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/context) · added 2026-09-12
