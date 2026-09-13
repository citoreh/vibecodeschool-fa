<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Cache tokens

> The share of a request's input served from the prefix cache. Heavily discounted, and the first thing to check when a session feels pricey.

*§01 The Model · also called: Cached tokens, Cache read tokens, Cache hit · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/cache-tokens)*

Cache tokens are the portion of a request's [input tokens](./input-tokens.md) that the [model provider](./model-provider.md) recognised from its [prefix cache](./prefix-cache.md) and didn't have to process again. They still count toward the [context window](./context-window.md) (the model sees them) but are billed at a fraction of the normal input rate and cost almost no latency. On a healthy coding session, the large majority of input on each request should be cache tokens.

They're the number to watch when a session feels expensive. If a usage readout shows a big context but few cache tokens, something is breaking the cache on every request: an instruction file that's regenerated each turn, a tool whose definition changes, or gaps between messages long enough for the cache to expire. If cache tokens are high and the bill is still climbing, the problem is simply that the window is too big, and [compaction](./compaction.md) is the fix.

Providers report them separately, and harnesses surface them. Learning to read that line ('cached' vs 'fresh' input) turns cost from a mystery into a diagnostic. Cache-write tokens are the other side: the first time a prefix is stored, some providers charge a small premium. That's fine as long as it's followed by many reads.

## In the tools

- Anthropic API: usage returns `cache_read_input_tokens` and `cache_creation_input_tokens` alongside plain input.
- OpenAI API: `cached_tokens` appears under prompt token details when caching kicks in.
- Claude Code: `/cost` splits the session's input into cached and uncached.

## In conversation

> “The status line says 180k context but the cost barely moved this turn.”
>
> “Most of it came back as cache tokens. You're paying for the new tool result, not the whole history.”

**Related:** [Model provider request](./model-provider-request.md) · [Usage limit](./usage-limit.md) · [Token](./token.md)

## Learn it in the school

- [Course 04 · Latency, Cost & Reliability Budgets](https://vibecodeschool.com/learn/aa-05-latency-cost-reliability)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/cache-tokens) · added 2026-09-12
