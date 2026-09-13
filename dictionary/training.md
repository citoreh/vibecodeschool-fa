<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Training

> How a model's weights get their values: predicting text at huge scale, then rounds of feedback that shape it into an assistant.

*§01 The Model · also called: Pre-training, Post-training · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/training)*

Training is how a model's [parameters](./parameters.md) get their values. In the first phase, pre-training, the network reads an enormous corpus of text and code and is nudged, token by token, toward better [next-token prediction](./next-token-prediction.md). Later phases (often called post-training) use curated examples and human or model feedback to make it follow instructions, use tools and decline harmful requests. All of this happens before you ever type a prompt.

The part people miss: training is over by the time you use the model. Nothing you say in Claude Code or Cursor updates the weights. The model isn't learning your codebase across sessions; it is re-reading whatever the [harness](./harness.md) puts in front of it each time. What feels like learning is a [memory system](./memory-system.md) or a project file being loaded into [context](./context.md).

Two consequences follow. First, the model's built-in knowledge stops at its [knowledge cutoff](./knowledge-cutoff.md), so anything newer has to be supplied. Second, post-training shapes personality as well as skill: an eagerness to agree ([sycophancy](./sycophancy.md)) and a tendency to produce confident text either way ([hallucination](./hallucination.md)) are side effects of how the model was rewarded. Fine-tuning on your own data is possible with some providers, but for coding work it's almost never the right first move.

## In the tools

- Anthropic API: models are used as-is with no per-user training; customisation happens through prompts, files and tools.
- OpenAI API: offers fine-tuning for some models, but coding agents like Codex run on the standard assistant models.

## In conversation

> “Can I train Claude on our internal framework?”
>
> “You could fine-tune, but loading the docs into context each session gets you most of the way with none of the setup.”

**Related:** [Parametric knowledge](./parametric-knowledge.md) · [Contextual knowledge](./contextual-knowledge.md) · [Effort](./effort.md)

## Learn it in the school

- [Course 04 · How LLMs Actually Work](https://vibecodeschool.com/learn/aa-01-how-llms-actually-work)
- [Course 04 · Finetuning: When It Pays Off](https://vibecodeschool.com/learn/aa-15-finetuning-fundamentals)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/training) · added 2026-09-12
