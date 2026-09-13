<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Next-token prediction

> The model's one trick: pick a likely next token, stick it on the end, go again. Prose, code and tool calls all come out this way.

*§01 The Model · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/next-token-prediction)*

Next-token prediction is the single operation a [model](./model.md) performs. Given the whole [context window](./context-window.md) so far, it produces a probability for every possible next [token](./token.md), one is chosen, it's appended to the sequence, and the whole thing runs again. A paragraph of prose, a hundred-line function and a structured [tool call](./tool-call.md) are all produced the same way, one piece at a time, with no separate 'planning' step outside the text.

This explains a lot of otherwise puzzling behaviour. The model can't go back and edit what it already emitted, so an early wrong assumption propagates through the rest of the answer. It can't 'run' code in its head; it predicts what running code would print, which is a very different thing. And because each token is sampled from a distribution, the same prompt can go a different way next time ([non-determinism](./non-determinism.md)).

Two habits follow. Get the important constraints in front of the model before it starts writing, because what comes first shapes everything after. And when it goes wrong early in a long output, stop and re-prompt rather than hoping it self-corrects mid-stream; asking it to reason first ([effort](./effort.md)) gives it text to condition on before the final answer.

## In the tools

- Most tools: streaming output is next-token prediction made visible; each word appears as it's sampled.
- Anthropic API: tool use is the model emitting a structured block token by token; the harness parses it once it's complete.

## In conversation

> “It wrote the wrong import on line one and then the whole file assumed it.”
>
> “That's next-token prediction: each line builds on the last. Fix the import in the prompt and let it regenerate.”

**Related:** [Inference](./inference.md) · [Parameters](./parameters.md) · [Hallucination](./hallucination.md)

## Learn it in the school

- [Course 04 · How LLMs Actually Work](https://vibecodeschool.com/learn/aa-01-how-llms-actually-work)
- [Course 05 · Chain-of-Thought Prompting](https://vibecodeschool.com/learn/pe-07-chain-of-thought)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/next-token-prediction) · added 2026-09-12
