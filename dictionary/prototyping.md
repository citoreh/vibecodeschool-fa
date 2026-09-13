<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Prototyping

> Building a quick, throwaway version to learn something, not to keep. With agents it's cheap enough to do before deciding anything.

*§07 Patterns of Work · also called: Throwaway prototype, Spike · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/prototyping)*

Prototyping is building the fast, disposable version of something to find out whether the idea works, what it feels like, or where the hard part is. The deliverable is the answer, not the code. Agents change the economics: a prototype that used to cost a day now costs a prompt and twenty minutes, which means you can afford to prototype before you commit to a [design concept](./design-concept.md), not after.

The danger is the prototype that doesn't get thrown away. A vibe-coded demo works in the happy path, someone likes it, and it quietly becomes the product, with no tests, guessed data shapes and a folder called `temp2`. Because agent output looks finished, the line between 'prototype' and 'v1' blurs faster than it did when a prototype looked rough.

Decide before you start which one you're building. For a prototype, drop the ceremony: no [spec](./spec.md), full [vibe coding](./vibe-coding.md) mode, minimal [human review](./human-review.md), a fresh [worktree](./worktree.md) or directory you can delete. Write down what you learned when it's done. Then, if it earns a real version, start that version clean, with the prototype as a reference in the [context](./context.md) rather than as the codebase you extend.

## In the tools

- Claude Code and Codex: a throwaway directory plus an auto-accept permission mode gives the fastest prototyping loop, since nothing needs approval.
- ChatGPT Work and Claude Cowork: good for prototyping documents, decks and dashboards before anyone builds software.

## In conversation

> “Should we design the onboarding flow first or just build it?”
>
> “Prototype three versions this afternoon, click through them, then write the spec for the one that felt right.”

**Related:** [One-shot](./one-shot.md) · [AFK](./afk.md) · [Checkpoint](./checkpoint.md) · [Sandbox](./sandbox.md)

## Learn it in the school

- [Course 02 · Generating Screens from a Sketch](https://vibecodeschool.com/learn/cm-07-screens-from-sketch)
- [Course 01 · Iterative Refinement](https://vibecodeschool.com/learn/cc-19-iterative-refinement)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/prototyping) · added 2026-09-12
