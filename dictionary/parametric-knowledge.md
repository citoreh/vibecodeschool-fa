<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Parametric knowledge

> What the model knows because it was in the training data, stored in its weights and frozen from that moment on.

*§04 Failure Modes · also called: Baked-in knowledge, Training knowledge · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/parametric-knowledge)*

Parametric knowledge is everything a [model](./model.md) knows without being told in the prompt. It was absorbed during [training](./training.md) and lives in the [parameters](./parameters.md): how Python works, what React looked like at the time, common bugs, idioms, the names of popular libraries and their older APIs. It is why an agent can write a working Express server from a one-line request with no documentation loaded.

The catch is that it is a snapshot. Nothing after the [knowledge cutoff](./knowledge-cutoff.md) is in there, and even things before it are compressed and approximate. When your project uses a framework version the model never saw, or a private internal library, its parametric knowledge does not go blank; it fills the gap with the nearest thing it does know, which is how you get last year's API under this year's package name.

Know which kind of fact you are relying on. For stable, widely used things, parametric knowledge is fast and usually right. For anything recent, niche or specific to your codebase, put the real material in the [context window](./context-window.md) so the model works from [contextual knowledge](./contextual-knowledge.md) instead. A good rule: if you would need to look it up, so does the model.

## In the tools

- Most tools: nothing in the harness updates what the model knows; docs lookups and web fetch are how fresh facts get into a request.
- Claude Code: a CLAUDE.md note like 'we use Tailwind v4 syntax, see docs/tailwind.md' steers the agent off stale parametric habits.

## In conversation

> “How does it know the whole Next.js router API without me pasting anything?”
>
> “Parametric knowledge, from training. Just check which version it's remembering before you trust it.”

**Related:** [Hallucination](./hallucination.md) · [Primary source](./primary-source.md) · [Inference](./inference.md)

## Learn it in the school

- [Course 04 · How LLMs Actually Work](https://vibecodeschool.com/learn/aa-01-how-llms-actually-work)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/parametric-knowledge) · added 2026-09-12
