<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Context engineering

> Deciding what goes into the context window, when, and in what order, so the agent sees what the task needs and nothing else.

*§06 Memory & Steering · also called: Context management, Context curation · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/context-engineering)*

Context engineering is the discipline of choosing what the [model](./model.md) sees on each request: which instructions, which files, which [tool results](./tool-result.md), which examples, and how much history. Where prompt engineering is about the wording of a request, context engineering is about the selection, ordering, timing, and budget of everything around it. The [context window](./context-window.md) is finite and every [token](./token.md) in it competes for the model's [attention](./attention-budget.md), so what you leave out matters as much as what you put in.

Most bad sessions are context problems, not model problems. The agent read the wrong files, or all the files, or a stale summary; the instructions file is a novel; the useful constraint is buried under three hundred lines of test output. The same model with a well-shaped window behaves like a different, sharper tool, which is why two people on the same harness get such different results.

The practical moves are simple. Point instead of paste: a [context pointer](./context-pointer.md) beats a wall of text. Load on demand through tools rather than up front. Keep [AGENTS.md](./agents-md.md) short and let [progressive disclosure](./progressive-disclosure.md) carry the rest. [Clear](./clearing.md) between tasks so one task's debris does not fill the next task's window. Push bulky work, like a large search or a log read, into a [subagent](./subagent.md) whose context is thrown away when it reports back. Treat the window as a budget you spend on purpose.

## In the tools

- Claude Code: subagents, `/clear`, `/compact` with instructions, and `@file` mentions are the everyday context-engineering controls.
- Antigravity: the knowledge base and per-task workspaces decide what each agent sees; keep tasks scoped so each window stays small.
- Codex: `AGENTS.md` scoping by directory keeps instructions local to the code they apply to.

## In conversation

> “I gave it everything: the whole repo, the design doc, the old thread. It's worse than before.”
>
> “That's a context engineering problem. You filled the window with things it has to read past.”
>
> “So what do I include?”
>
> “The two files it will edit, the test that should pass, and a pointer to the doc. Let it fetch anything else.”

**Related:** [Harness engineering](./harness-engineering.md) · [Smart zone](./smart-zone.md) · [Handoff](./handoff.md)

## Learn it in the school

- [Course 04 · Context Engineering](https://vibecodeschool.com/learn/aa-06-context-engineering)
- [Course 05 · Long-Context Prompting](https://vibecodeschool.com/learn/pe-20-long-context-prompting)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/context-engineering) · added 2026-09-12
