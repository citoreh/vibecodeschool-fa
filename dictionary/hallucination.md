<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Hallucination

> Output that is fluent, confident, and wrong: an invented API, a misquoted file, a test result that never happened.

*§04 Failure Modes · also called: Confabulation, Fabrication · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/hallucination)*

A hallucination is confident model output with nothing real behind it. Because a [model](./model.md) produces text by [next-token prediction](./next-token-prediction.md), it will produce a plausible answer whether or not it has a basis for one; there is no built-in 'I don't know' unless the training or the prompt made room for it. In coding, that means a function that looks like it belongs to the library but doesn't, a flag that was never in the CLI, or a summary of a file that misstates what the file says.

It helps to separate two kinds. The first is missing knowledge: the model reaches for a fact it never learned, or learned before the [knowledge cutoff](./knowledge-cutoff.md), and fills the gap. The second is drift from the [context](./context.md) it was given: the file is right there in the window, but the model paraphrases it wrong, usually late in a long session once [attention degradation](./attention-degradation.md) has set in. The first is fixed by loading a [primary source](./primary-source.md); the second by shortening the session.

The working defence is verification the model does not control. Have the agent run the code, not describe it; make a passing test the definition of done; ask for line-numbered citations when it claims a file says something. And treat the confident tone as noise: fluency and correctness are produced by the same mechanism, so one tells you nothing about the other.

## In the tools

- Claude Code: web fetch and doc lookups put a real source into context; asking the agent to run the code catches invented APIs immediately.
- Cursor: attaching a library's docs with `@Docs` gives the model the real surface to work from instead of its memory of it.

## In conversation

> “It used `db.upsertMany()` and swears it's in the ORM docs. It isn't.”
>
> “Hallucinated. Load the actual docs page into context and have it re-check every method it calls.”

**Related:** [Sycophancy](./sycophancy.md) · [Parametric knowledge](./parametric-knowledge.md) · [Automated check](./automated-check.md)

## Learn it in the school

- [Course 05 · Why Models Hallucinate](https://vibecodeschool.com/learn/pe-13-why-models-hallucinate)
- [Course 05 · Calibration: Getting 'I Don't Know'](https://vibecodeschool.com/learn/pe-14-calibration-and-uncertainty)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/hallucination) · added 2026-09-12
