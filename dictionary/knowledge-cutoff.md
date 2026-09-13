<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Knowledge cutoff

> The date the model's training data ends; anything released after it is unknown to the model unless you load it into context.

*§04 Failure Modes · also called: Training cutoff, Cutoff date · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/knowledge-cutoff)*

The knowledge cutoff is the point in time after which a [model](./model.md) has seen nothing. [Training](./training.md) data is collected up to a date, the model is trained, tested and released some months later, and then used for a year or more. So at any moment the model's picture of the world is stale by somewhere between several months and a couple of years, and nothing in the [harness](./harness.md) moves that date.

For coding this bites in a specific way: libraries move faster than models. A package released after the cutoff, a breaking major version, a renamed config option, a new CLI flag; the model has no [parametric knowledge](./parametric-knowledge.md) of any of it, and by default it will not say so. It will write the old API with total confidence, and the resulting error will look like your mistake rather than its blind spot.

Assume the cutoff is a problem whenever the thing you are using is newer than about a year old. Load the current docs or the installed package's own type definitions into the [context window](./context-window.md), and tell the agent explicitly which version you are on. A sentence in your project file ('Next 15, app router, Tailwind v4') prevents a whole category of confident regressions.

## In the tools

- Anthropic API: each model publishes a training cutoff in its docs; check it before trusting the model on a recent library.
- Claude Code: fetching a docs page or reading `node_modules/<pkg>/README.md` is the fastest way past the cutoff.

## In conversation

> “It keeps generating the old config format and then blaming the build for 'a bug'.”
>
> “The format changed after its knowledge cutoff. Paste the migration guide and tell it which version we're on.”

**Related:** [Hallucination](./hallucination.md) · [Contextual knowledge](./contextual-knowledge.md) · [Primary source](./primary-source.md)

## Learn it in the school

- [Course 05 · Prompt Versioning & Model Migration](https://vibecodeschool.com/learn/pe-24-prompt-versioning-and-migration)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/knowledge-cutoff) · added 2026-09-12
