<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Usage limit

> The cap on how much agent work your plan or API key allows in a window. Hitting it pauses you; it isn't the context window.

*§01 The Model · also called: Rate limit, Usage cap, 5-hour window, Weekly limit · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/usage-limit)*

A usage limit is the ceiling your plan or API key puts on how much model work you can do in a period. Subscription plans (Claude Pro and Max, ChatGPT Plus and Pro) meter usage in rolling windows, commonly a few hours plus a weekly cap, and pause you when it's spent. API keys meter differently: requests and [tokens](./token.md) per minute, plus whatever spend tier your account sits in. Both are set by the [model provider](./model-provider.md), not the harness.

The confusing part is that the limit drains in tokens, and tokens are mostly [input tokens](./input-tokens.md). A session with a bloated [context window](./context-window.md) burns the allowance many times faster than a lean one, because every [model provider request](./model-provider-request.md) re-sends the whole history. People who 'barely did anything' and still hit the wall usually had one giant session open all day. And a usage limit is not a context limit: one says stop for now, the other says this conversation can't hold more.

To stretch it: keep sessions short and focused, [compact](./compaction.md) before the window balloons, use a cheaper model for grunt work and the strong one for planning, and keep the [prefix cache](./prefix-cache.md) warm so repeated input is billed as cheap [cache tokens](./cache-tokens.md). If you're regularly capped, an API key with pay-as-you-go pricing removes the window but makes every token visible on a bill, which is its own kind of discipline.

## In the tools

- Claude Code: subscription limits reset on a rolling window; `/status` shows the plan, and `/cost` shows what the session consumed.
- Codex: ChatGPT-plan usage has its own windows; `/status` reports where you stand.
- Anthropic API: rate limits are per minute and scale with your usage tier; spend limits are set in the console.

## In conversation

> “It says I've hit my limit until 4pm and I only ran three tasks.”
>
> “Three tasks in one 200k-token session. Each request re-read all of it. Split the work into fresh sessions next time.”

**Related:** [Effort](./effort.md) · [Output tokens](./output-tokens.md) · [Headless mode](./headless-mode.md)

## Learn it in the school

- [Course 03 · Models, Rate Limits, and Spend](https://vibecodeschool.com/learn/ag-16-cost-budgeting)
- [Course 04 · Latency, Cost & Reliability Budgets](https://vibecodeschool.com/learn/aa-05-latency-cost-reliability)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/usage-limit) · added 2026-09-12
