<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Input tokens

> Everything the model reads on a request: instructions, history, tool definitions, results. Cheap per token, but there are a lot of them.

*§01 The Model · also called: Prompt tokens · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/input-tokens)*

Input tokens are everything the [harness](./harness.md) sends up in a [model provider request](./model-provider-request.md): the [system prompt](./system-prompt.md), every message so far, the definitions of every available [tool](./tool.md), and every tool result that's been fed back. They're the 'reading' side of the bill and are priced lower per token than [output tokens](./output-tokens.md), but there are a lot more of them, and their count grows on every turn because the whole history is re-sent.

That growth is the trap. Early in a session a request might be a few thousand input tokens. After an hour of reading files and running tests it can be well over a hundred thousand, and every additional request pays for all of it again. A session that feels slow and expensive late in the day is almost always an input-token problem, not an output one.

Two things help. The [prefix cache](./prefix-cache.md) lets the provider skip re-processing the unchanged prefix, so repeated input is billed as cheaper [cache tokens](./cache-tokens.md). And you control what enters the window: read the files that matter rather than the directory, pipe noisy command output through `head` or a grep, and [compact](./compaction.md) or start fresh once the useful part of the history is behind you.

## In the tools

- Claude Code: `/context` breaks the window down by what's occupying it; most of it is input on every request.
- OpenAI API: usage reports `prompt_tokens`, the same idea under a different name.

## In conversation

> “Ninety percent of my spend is input. Is that normal?”
>
> “Yes, in a long agent session. The fix is a shorter context, not fewer replies.”

**Related:** [Token](./token.md) · [Context window](./context-window.md) · [Usage limit](./usage-limit.md)

## Learn it in the school

- [Course 04 · Latency, Cost & Reliability Budgets](https://vibecodeschool.com/learn/aa-05-latency-cost-reliability)
- [Course 05 · Long-Context Prompting](https://vibecodeschool.com/learn/pe-20-long-context-prompting)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/input-tokens) · added 2026-09-12
