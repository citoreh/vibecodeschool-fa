<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Parameters

> The billions of numbers a model is made of, fixed once training ends. Also called weights. What the model knows by heart lives in them.

*§01 The Model · also called: Weights · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/parameters)*

Parameters are the numbers a [model](./model.md) is made of. During [training](./training.md) they are adjusted, trillions of times, until the network gets good at [next-token prediction](./next-token-prediction.md); after that they're frozen. When you hear '8B' or '70B', that's the parameter count in billions. Frontier models from Anthropic, OpenAI and Google don't publish theirs, but they're far larger.

Everything the model 'knows' without being told is stored across these numbers, which is what [parametric knowledge](./parametric-knowledge.md) means. There is no lookup table of facts inside; there is a giant tangle of weights that happens to produce the right continuation most of the time. That's why a model can be fluent about a library and still wrong about its current API: the weights encode a blurred average of what it read up to its [knowledge cutoff](./knowledge-cutoff.md).

Parameter count matters in two practical ways. It sets how much memory the model needs, which is why a 7B model runs on a laptop and a 400B one doesn't. And it roughly tracks capability, though training quality and [effort](./effort.md) settings matter just as much. A session never rewrites the parameters; every correction you make lives in [context](./context.md), and the weights stay exactly as shipped.

## In the tools

- Ollama: model tags like `llama3:8b` name the parameter count; bigger tags need more RAM or VRAM.
- Most tools: hosted models hide their parameter counts; you pick by tier (fast and cheap vs slow and strong), not by size.

## In conversation

> “If I keep correcting it, will it learn my codebase?”
>
> “Not in the weights. Parameters are fixed after training. Put the rules in CLAUDE.md so they're loaded every session instead.”

**Related:** [Inference](./inference.md) · [Memory system](./memory-system.md) · [AGENTS.md](./agents-md.md)

## Learn it in the school

- [Course 04 · How LLMs Actually Work](https://vibecodeschool.com/learn/aa-01-how-llms-actually-work)
- [Course 04 · Running Models Locally with Ollama](https://vibecodeschool.com/learn/aa-17-local-models-ollama)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/parameters) · added 2026-09-12
