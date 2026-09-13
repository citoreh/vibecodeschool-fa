<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Token

> The unit a model reads and writes in — a word fragment, a little shorter than a word — and the unit every limit and price uses.

*§01 The Model · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/token)*

A token is the chunk of text a [model](./model.md) actually processes. Text is split by a tokenizer into pieces that are usually a word, part of a word, or a punctuation mark, and the model reads and writes these pieces rather than characters. In English prose a token averages around four characters, so a thousand words is roughly 1,300 tokens. Code tokenizes worse: indentation, brackets and symbols each cost their own tokens.

Every limit and every price is in tokens. The [context window](./context-window.md) is a token count. [Input tokens](./input-tokens.md) and [output tokens](./output-tokens.md) are billed separately. Your [usage limit](./usage-limit.md) drains in tokens. That's why a pasted log file or a giant JSON blob can quietly wreck a session: it looks like one message to you, but to the model it's tens of thousands of tokens competing for space.

You don't need to count precisely, but you do need a sense of scale. A typical source file is a few thousand tokens; a test run's output can be more; a whole repo is usually far beyond the window. Load what the task touches, use search instead of reading everything, and trim noisy tool output before it lands in [context](./context.md).

## In the tools

- Claude Code: `/context` and `/cost` show how many tokens the session has used and where they went.
- Codex: `/status` reports token usage for the current session.
- Anthropic API: the count-tokens endpoint tells you a prompt's size before you send it.

## In conversation

> “I pasted the full stack trace and the whole package-lock. Was that bad?”
>
> “The lock file alone is probably fifty thousand tokens. That's a chunk of the window gone on something it didn't need.”

**Related:** [Next-token prediction](./next-token-prediction.md) · [Prefix cache](./prefix-cache.md) · [Compaction](./compaction.md)

## Learn it in the school

- [Course 04 · How LLMs Actually Work](https://vibecodeschool.com/learn/aa-01-how-llms-actually-work)
- [Course 05 · Long-Context Prompting](https://vibecodeschool.com/learn/pe-20-long-context-prompting)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/token) · added 2026-09-12
