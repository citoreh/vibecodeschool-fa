<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Context window

> The fixed-size buffer of tokens a model can read in one request; if something isn't in it, the model can't see it.

*§02 Sessions, Context Windows & Turns · also called: Context length, Window · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/context-window)*

The context window is the maximum amount of text, measured in [tokens](./token.md), that a model can take in on a single [model provider request](./model-provider-request.md). The [system prompt](./system-prompt.md), every message in the session, every file the agent read and every command result it saw all have to fit inside it together. The size is a property of the model: current frontier models offer somewhere between roughly 200k and a million tokens, and the number moves with each release.

The window fills faster than people expect. A coding session appends constantly: your prompts are small, but one `cat` of a large file or a noisy test run can consume tens of thousands of tokens in a single step. When the window is nearly full, the [harness](./harness.md) has to do something: [compact](./compaction.md) the history, drop old turns, or refuse to continue. Long before that point, quality usually slips, because the model is weighing more material than it can hold in focus (see [attention degradation](./attention-degradation.md)).

Treat the window as a budget rather than a limit. Load what the task needs and no more, prefer targeted reads over whole-repo dumps, and open a fresh [session](./session.md) for a new task instead of stacking it on the old one. A bigger window is not a licence to be careless about what goes in; it just moves the cliff further out.

**Avoid:** Calling it 'memory'. The window is working space for the current session and is discarded when the session ends; anything you want remembered has to live in a file and be reloaded.

## In the tools

- Claude Code: an indicator shows remaining context as the session grows; `/compact` frees space and `/clear` empties the window entirely.
- Anthropic API: the window size is per model and covers both the input you send and the tokens the model generates in reply.

## In conversation

> “The agent read every file in `src/` and now its answers are vague.”
>
> “You spent most of the context window on files it didn't need. Clear, then point it at the two modules that matter.”

**Related:** [Input tokens](./input-tokens.md) · [Smart zone](./smart-zone.md) · [Clearing](./clearing.md)

## Learn it in the school

- [Course 05 · Long-Context Prompting](https://vibecodeschool.com/learn/pe-20-long-context-prompting)
- [Course 01 · The Agentic Loop](https://vibecodeschool.com/learn/cc-04-the-agentic-loop)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/context-window) · added 2026-09-12
