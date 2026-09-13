<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Inference

> Using the model rather than training it. Every reply, edit and tool call you see comes from an inference pass; the weights never move.

*§01 The Model · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/inference)*

Inference is the act of running a trained [model](./model.md): feed it a [context window](./context-window.md) full of tokens, get back new tokens. Nothing in the weights changes; the model is being used, not trained. Each [model provider request](./model-provider-request.md) triggers one inference pass, and inside that pass the model emits its answer [token](./token.md) by token, which is why responses stream in rather than appear at once.

Inference is where cost and latency come from. The provider runs the model on GPUs, charges per token processed, and needs time proportional to how much it has to read ([input tokens](./input-tokens.md)) and how much it has to write ([output tokens](./output-tokens.md)). A long session with a bloated context makes every single inference pass slower and more expensive, because the model re-reads the whole window each time.

You can run inference locally with tools like Ollama or llama.cpp, trading capability for privacy and zero per-token cost. For agentic coding that's usually a step down: the models that fit on a laptop are noticeably weaker at multi-step work. The practical levers are elsewhere: keep context lean, use a cheaper model for routine steps, and let the [prefix cache](./prefix-cache.md) absorb what repeats.

## In the tools

- Ollama: `ollama run <model>` does inference on your own machine; speed depends on your GPU and the model size.
- Claude Code: each turn may trigger several inference passes, one per tool call round trip; `/cost` shows what they added up to.

## In conversation

> “Why is every response getting slower as the day goes on?”
>
> “Inference re-reads the whole session each turn. Your context is huge now. Compact it or start fresh.”

**Related:** [Model provider](./model-provider.md) · [Compaction](./compaction.md) · [Non-determinism](./non-determinism.md)

## Learn it in the school

- [Course 04 · Latency, Cost & Reliability Budgets](https://vibecodeschool.com/learn/aa-05-latency-cost-reliability)
- [Course 04 · Running Models Locally with Ollama](https://vibecodeschool.com/learn/aa-17-local-models-ollama)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/inference) · added 2026-09-12
