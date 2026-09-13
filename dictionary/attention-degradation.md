<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Attention degradation

> The slow drop in output quality as a session grows and every token's attention is spread across more competing material.

*§04 Failure Modes · also called: Context rot, Lost in the middle · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/attention-degradation)*

Attention degradation is what happens to a [model's](./model.md) output as the [context window](./context-window.md) fills. Each [token](./token.md) has a fixed [attention budget](./attention-budget.md); as the [session](./session.md) accumulates file reads, test logs and old plans, that budget gets split across ever more tokens, and the signal on the pairs that matter thins out. The model is not tired or broken. It is doing the same computation over a worse ratio of relevant to irrelevant material.

You notice it as a slide rather than a break. Answers get more generic, an earlier instruction is quietly dropped, a mistake it fixed at turn ten comes back at turn thirty, and it starts describing files slightly wrong even though they are right there in the window. Because the decline is gradual there is no error to react to, and the instinct to keep going and re-explain adds more [context](./context.md) and speeds the slide.

The remedy is unglamorous: keep sessions short and tasks bounded, [compact](./compaction.md) at natural checkpoints, and start a fresh session with a written [handoff](./handoff.md) when the current one is deep in the murk. Bigger windows delay the onset but do not remove it; the useful working length of a session is well short of its maximum.

## In the tools

- Claude Code: the context indicator and `/context` show how full the window is; `/compact` and `/clear` are the two recovery moves.
- Antigravity: long-running agents can be handed a fresh task with a summary rather than continued indefinitely in one thread.

## In conversation

> “Same prompt, same repo. Two hours in and it's producing junk it would never have written at the start.”
>
> “Attention degradation. The window's mostly logs now. Write down where you are, clear, and reload just the plan.”

**Related:** [Smart zone](./smart-zone.md) · [Attention relationship](./attention-relationship.md) · [Clearing](./clearing.md)

## Learn it in the school

- [Course 05 · Long-Context Prompting](https://vibecodeschool.com/learn/pe-20-long-context-prompting)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/attention-degradation) · added 2026-09-12
