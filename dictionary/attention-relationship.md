<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Attention relationship

> The link between any two tokens in the context; the model weighs each pair, and there are far more pairs than tokens.

*§04 Failure Modes · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/attention-relationship)*

An attention relationship is the connection between two [tokens](./token.md) in the [context window](./context-window.md). When a [model](./model.md) processes a request, each token looks at every other token and assigns it a weight: how much does that one matter for understanding this one? The variable name on line 40 and its declaration on line 3 have a strong relationship; the variable and a log line from an unrelated test run have a weak one. This pairwise weighing is the attention mechanism that transformers are built on.

The number of relationships grows much faster than the context does. Double the tokens and you roughly quadruple the pairs the model has to sort through, and the pairs that carry real meaning (a bug and its cause, a rule and the code it governs) become a smaller and smaller share of the total. Nothing about the important pairs got weaker; they are simply outnumbered.

You do not manage attention relationships directly, but you shape them by what you load. A tight [context](./context.md) with only the relevant files keeps the meaningful pairs dense; a sprawling session with dozens of unrelated reads buries them. This is the mechanism underneath [attention budget](./attention-budget.md) and [attention degradation](./attention-degradation.md), and the reason 'just load more' so often makes results worse.

## In the tools

- Most tools: there is no dial for this; the lever you have is what you put in the window and how long you let a session run.

## In conversation

> “The bug report is in the context and so is the buggy function. Why can't it connect them?”
>
> “There's eighty thousand tokens of unrelated test output between them. The attention relationship is still there; it's just one pair among millions now.”

**Related:** [Smart zone](./smart-zone.md) · [Training](./training.md) · [Next-token prediction](./next-token-prediction.md)

## Learn it in the school

- [Course 04 · How LLMs Actually Work](https://vibecodeschool.com/learn/aa-01-how-llms-actually-work)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/attention-relationship) · added 2026-09-12
