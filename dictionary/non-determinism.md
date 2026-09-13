<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Non-determinism

> Run the same prompt twice and you can get two different answers. Sampling, batching and silent provider updates all contribute.

*§01 The Model · also called: Nondeterminism · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/non-determinism)*

Non-determinism means the same prompt does not reliably give the same answer. The main cause is sampling: [next-token prediction](./next-token-prediction.md) produces a probability distribution, and the [model](./model.md) picks from it, so two runs can diverge at the first uncertain token and never reconverge. Even at temperature zero, floating-point arithmetic on batched GPU requests introduces small differences, and some architectures route tokens through different internal experts depending on what else is in the batch.

There's a second, sneakier source: the thing you're calling changes under you. Providers update models, [harnesses](./harness.md) revise their [system prompt](./system-prompt.md), and a [tool](./tool.md) gets a new description. 'It worked yesterday' is a weak claim in agentic coding, and the instinct to find the one prompt that always works is chasing something that doesn't exist.

Design for variance instead of fighting it. Put an [automated check](./automated-check.md) behind every agent change so a bad roll fails loudly. Rerun rather than re-argue when a result looks like a fluke. Pin exact model versions in API code. And write your instructions so the intended path is overwhelmingly the most likely one: clear constraints narrow the distribution far more than pleading does.

## In the tools

- Anthropic API: `temperature` shapes sampling but doesn't remove variance; dated model IDs at least pin which model you get.
- Claude Code: rerunning a turn after `/rewind` can land on a different plan; treat each run as a fresh sample.

## In conversation

> “I ran the exact same prompt twice and got two different migrations.”
>
> “Non-determinism. Neither is 'the' answer. Add a test that pins the behaviour you want and rerun until it passes.”

**Related:** [Hallucination](./hallucination.md) · [Automated review](./automated-review.md) · [Effort](./effort.md)

## Learn it in the school

- [Course 05 · Testing Prompts Like Code](https://vibecodeschool.com/learn/pe-18-testing-prompts-like-code)
- [Course 05 · Self-Consistency](https://vibecodeschool.com/learn/pe-09-self-consistency)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/non-determinism) · added 2026-09-12
