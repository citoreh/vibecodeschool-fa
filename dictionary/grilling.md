<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Grilling

> Having the agent interview you, question by question, until the requirements are fully resolved before it writes anything.

*§07 Patterns of Work · also called: Grill me, Interrogation, Requirements interview · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/grilling)*

Grilling flips the usual direction of a prompt: instead of you describing the task, the [agent](./agent.md) asks the questions. You tell it what you want to build and instruct it to grill you, one question at a time, until it has no open questions left. The output is not code but a resolved understanding, usually written up as a [design concept](./design-concept.md) or a [spec](./spec.md).

It works because the model is good at spotting gaps you can't see in your own request. You know what you meant by 'sync the data', so you never said which direction, how often, or what happens on conflict. The agent doesn't know, and in a normal run it would pick answers for you. Grilling surfaces those choices while they're cheap to make, before hours of [AFK](./afk.md) work are built on them.

Give it rules so it stays useful: one question per [turn](./turn.md), no leading questions, stop when the remaining questions are about implementation detail rather than intent, then write the result down. Keep the session short and the [context](./context.md) clean, and finish by asking for the spec as a file so it survives as a [handoff artifact](./handoff-artifact.md) for the session that actually builds.

## In the tools

- Claude Code: plan mode with an instruction to interview you before planning; the agent can pause on each question.
- Most tools: a reusable prompt or slash command that says 'grill me on this until nothing is ambiguous' works in any chat harness.

## In conversation

> “It asked me eleven questions before it wrote a line. Is that normal?”
>
> “That's the grilling. Question nine was the one about deleted users, right? That would have been a bug in the PR.”

**Related:** [Human-in-the-loop](./human-in-the-loop.md) · [One-shot](./one-shot.md) · [Slash command](./slash-command.md) · [Prototyping](./prototyping.md)

## Learn it in the school

- [Course 05 · Prompting AI Agents](https://vibecodeschool.com/learn/pe-22-prompting-ai-agents)
- [Course 01 · Plan Mode](https://vibecodeschool.com/learn/cc-15-plan-mode)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/grilling) · added 2026-09-12
