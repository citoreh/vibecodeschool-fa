<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Automated check

> A mechanical pass/fail test the harness or CI runs on the agent's work: types, lint, tests, build. Cheap, fast, no judgement.

*§07 Patterns of Work · also called: Check, CI check, Verification step · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/automated-check)*

An automated check is anything that can say yes or no about the agent's work without a person looking: the type checker, the linter, the test suite, a build, a schema validation, a link checker. It has a definite answer and it runs in seconds or minutes. It is the cheapest feedback an [agent](./agent.md) can get, and unlike a human it never gets tired of running.

Checks matter more with agents than with people because the agent will happily continue past a mistake it can't see. A [hallucinated](./hallucination.md) method name compiles in the agent's head but not in the compiler. Without a check, that error surfaces three files later as a confusing failure; with one, the agent gets a [tool result](./tool-result.md) saying exactly what broke and fixes it in the next [turn](./turn.md).

Wire the checks into the loop rather than running them yourself at the end. Tell the agent in [AGENTS.md](./agents-md.md) which command to run after every change, or use [hooks](./hooks.md) to run it automatically after each edit. The stricter and faster your checks, the further you can let the agent run [AFK](./afk.md). What checks can't judge (taste, product sense, whether the feature is the right feature) is the job of [human review](./human-review.md).

## In the tools

- Claude Code: a post-edit hook can run the type checker or tests after every change and feed failures straight back to the agent.
- GitHub: CI on the pull request is the last automated check before a human sees the work.

## In conversation

> “It refactored the whole module and the tests still pass. Do I still need to read it?”
>
> “The checks tell you it didn't break anything you already tested. They don't tell you it's good. Skim the diff.”

**Related:** [Automated review](./automated-review.md) · [Harness engineering](./harness-engineering.md) · [Spec](./spec.md)

## Learn it in the school

- [Course 01 · Running Tests with Claude](https://vibecodeschool.com/learn/cc-08-running-tests)
- [Course 01 · Hooks: Pre and Post Tool](https://vibecodeschool.com/learn/cc-16-hooks)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/automated-check) · added 2026-09-12
