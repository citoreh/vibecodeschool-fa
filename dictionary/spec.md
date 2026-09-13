<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Spec

> A written description of what to build and how you'll know it's right, agreed before the agent starts writing code.

*§05 Handoffs · also called: Specification, PRD, Design doc · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/spec)*

A spec is the written statement of what the work should produce: the behaviour, the constraints, the edge cases, and how success will be checked. For an [agent](./agent.md) it is the most important input to a task, because a coding agent will happily build the wrong thing with great confidence. The spec converts your intent, which lives in your head, into [context](./context.md) the agent can actually use.

Without one, the agent fills every gap with its own guess. Ambiguity you would have caught in a five-minute conversation becomes a merged implementation of the wrong idea, and in an [AFK](./afk.md) run there is nobody to ask. A missing spec also makes review harder: you cannot tell whether the result is right when nobody wrote down what right means.

Write specs at the level of behaviour, not code. Say what happens when the input is empty, what the API returns, what must not change. Include the [checks](./automated-check.md) that will prove it: tests to add, commands that must pass. Many people build the spec through [grilling](./grilling.md), letting the agent interrogate the idea before anything is written. Then commit the spec so it survives [clearing](./clearing.md) and doubles as a [handoff artifact](./handoff-artifact.md).

## In the tools

- Claude Code: draft the spec in plan mode, save it to a file, and reference it from CLAUDE.md or the task prompt.
- Antigravity: the implementation plan the manager produces is a spec you approve before execution starts.
- Most tools: a spec in the repo outlives any single chat; a spec that only lives in the prompt dies with the session.

## In conversation

> “It built a whole notifications system and it's not what I meant at all.”
>
> “What did the spec say?”
>
> “There wasn't one. I described it in the prompt.”
>
> “Write the spec first next time. Three paragraphs and a list of tests would have caught this.”

**Related:** [Plan mode](./plan-mode.md) · [Ticket](./ticket.md) · [Design concept](./design-concept.md) · [One-shot](./one-shot.md)

## Learn it in the school

- [Course 01 · Spec → Tests → Code](https://vibecodeschool.com/learn/cc-18-spec-tests-code)
- [Course 01 · Writing Tests-First](https://vibecodeschool.com/learn/cc-24-tests-first)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/spec) · added 2026-09-12
