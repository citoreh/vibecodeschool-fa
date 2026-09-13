<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Attention budget

> The fixed amount of focus each token can spread across the rest of the context; more context means thinner slices.

*§04 Failure Modes · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/attention-budget)*

The attention budget is the finite amount of influence a [token](./token.md) has to distribute over every other token in the [context window](./context-window.md). The weights across all of its [attention relationships](./attention-relationship.md) add up to a fixed total, so when the [context](./context.md) grows, each token's budget is divided among more candidates. A short, focused request lets the important tokens spend most of their budget on each other; a bloated one spreads the same budget across thousands of bystanders.

This is why you can have a fact plainly in the window and still get an answer that ignores it. The instruction you gave in message three is still present, but by turn forty it is competing with a mountain of file contents and command output for the [model's](./model.md) attention, and it loses a little on every request. The instruction was not forgotten; it was outvoted.

Spend the budget on purpose. Load fewer, more relevant files; summarise noisy output before it enters the transcript; restate the one rule that matters in the message where it matters, rather than trusting a rule from an hour ago to still carry weight. When a session has grown past the point where focus holds, [clearing](./clearing.md) or [compaction](./compaction.md) resets the budget.

## In the tools

- Claude Code: `/context` shows what is competing for attention right now; `/compact` with a focus instruction keeps the parts you name.
- Most tools: rules in a project instruction file are re-sent near the front of every request, which is why they hold up better than chat messages.

## In conversation

> “I put 'never edit the migrations folder' in my first message and it just edited a migration.”
>
> “Forty turns later that line is a tiny slice of the attention budget. Repeat the rule where it counts, or put it in CLAUDE.md.”

**Related:** [Attention degradation](./attention-degradation.md) · [Smart zone](./smart-zone.md) · [AGENTS.md](./agents-md.md)

## Learn it in the school

- [Course 05 · Long-Context Prompting](https://vibecodeschool.com/learn/pe-20-long-context-prompting)
- [Course 04 · Context Engineering](https://vibecodeschool.com/learn/aa-06-context-engineering)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/attention-budget) · added 2026-09-12
