<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Prefix cache

> The provider remembers the start of your last prompt, so the next request that begins the same way is faster and much cheaper.

*§01 The Model · also called: Prompt caching, Prompt cache · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/prefix-cache)*

The prefix cache is a [model provider](./model-provider.md) feature that stores the processed form of the start of your prompt so the next [model provider request](./model-provider-request.md) can skip re-reading it. Because a coding [session](./session.md) re-sends the same [system prompt](./system-prompt.md), tool definitions and conversation history on every request, most of each request is identical to the one before. A cache hit turns those [input tokens](./input-tokens.md) into much cheaper [cache tokens](./cache-tokens.md) and shortens the wait before the first new token.

The catch is the word prefix. Caching works from the start of the prompt up to the first change; anything after that point is processed fresh. Change something early (edit the system prompt, reorder tools, alter an old message) and the whole cache from there onward is lost. On most providers a cache that sits idle for a few minutes is dropped, so a long coffee break can mean the next request re-pays for the full context.

Harnesses like Claude Code and Codex handle this automatically and structure requests so the stable parts come first. Your part is to keep the stable parts stable: don't churn project instructions mid-session, avoid tools that inject changing timestamps at the top of the context, and keep working steadily rather than in bursts separated by long gaps.

## In the tools

- Anthropic API: prompt caching uses explicit cache breakpoints; cache reads are billed at a large discount, cache writes at a small premium.
- OpenAI API: caching is automatic for prompts past a minimum length, with discounted cached input.
- Claude Code: caching is on by default; `/cost` shows how much of the input was served from cache.

## In conversation

> “Why did the first message after lunch cost more than the whole morning?”
>
> “Prefix cache expired. It re-processed the entire session from scratch on that one request.”

**Related:** [Context window](./context-window.md) · [Effort](./effort.md) · [Harness](./harness.md)

## Learn it in the school

- [Course 04 · Latency, Cost & Reliability Budgets](https://vibecodeschool.com/learn/aa-05-latency-cost-reliability)
- [Course 04 · Function Calling & Structured Outputs](https://vibecodeschool.com/learn/aa-03-function-calling-structured-outputs)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/prefix-cache) · added 2026-09-12
