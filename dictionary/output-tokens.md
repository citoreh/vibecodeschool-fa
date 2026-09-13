<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Output tokens

> What the model writes: replies, code, tool calls, hidden thinking. Produced one by one, so they set the wait, and they cost the most.

*§01 The Model · also called: Completion tokens · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/output-tokens)*

Output tokens are what the [model](./model.md) writes back on each [model provider request](./model-provider-request.md): the visible reply, the code it produces, the structured [tool call](./tool-call.md) it emits, and any hidden reasoning when [effort](./effort.md) is turned up. They're generated one at a time by [next-token prediction](./next-token-prediction.md), which makes them slow to produce, and providers price them several times higher than [input tokens](./input-tokens.md) to match.

Most sessions spend far more on input than output, so output tokens are rarely the cost problem. They are the latency problem. A model rewriting a 600-line file from scratch is emitting thousands of tokens you then wait for, when a targeted diff would have been fifty. Extended thinking has the same shape: minutes of reasoning tokens on a task that didn't need any.

Ask for edits, not rewrites, and let the harness apply diffs. Keep reasoning effort proportional to the difficulty. When you want a long artefact (a spec, a migration plan), that's a fine use of output tokens; when you want a one-line change, a long answer is a smell, not a bonus.

## In the tools

- Claude Code: file edits are applied as diffs, so output stays small; thinking tokens show up under output in `/cost`.
- Anthropic API: `max_tokens` caps output per request; thinking, if enabled, counts against it.

## In conversation

> “It regenerated the entire component to change one className.”
>
> “That's a few thousand output tokens for a five-token change. Tell it to edit in place.”

**Related:** [Inference](./inference.md) · [Token](./token.md) · [Usage limit](./usage-limit.md)

## Learn it in the school

- [Course 04 · Latency, Cost & Reliability Budgets](https://vibecodeschool.com/learn/aa-05-latency-cost-reliability)
- [Course 05 · Reasoning Models vs CoT Prompts](https://vibecodeschool.com/learn/pe-12-reasoning-models-vs-cot)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/output-tokens) · added 2026-09-12
