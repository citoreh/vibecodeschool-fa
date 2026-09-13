<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Vibe coding

> Building software by describing what you want to an agent and judging the result rather than reading every line of code.

*§07 Patterns of Work · also called: Vibecoding · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/vibe-coding)*

Vibe coding is building software by telling an [agent](./agent.md) what you want and steering by outcomes rather than by reading code. Andrej Karpathy coined the phrase in early 2025 for a mode of fully giving in to the vibes and forgetting the code exists: you describe, the agent writes, you run it, you describe the next change. The code is still there; you've just stopped treating it as the thing you author.

The term split almost immediately. To critics it means unreviewed slop shipped by people who can't read what they built, and there is plenty of that. To people who do it well it means something narrower: a tight loop of prompt, run, look, correct, with a person who knows what 'working' looks like at the controls. Same tools, very different results, and the difference is the operator.

The honest rule is about stakes. Full vibe mode, where nobody reads the code, is fine for prototypes, personal tools, one-off scripts and anything you can throw away. It is not fine for production systems, money, or other people's data; there the loop keeps its shape but [human review](./human-review.md), [automated checks](./automated-check.md) and a written [spec](./spec.md) come back in. This school teaches the second kind: you don't have to write the code, but you do have to be able to judge it.

## In the tools

- Claude Code: the prompt, edit, run, correct loop in the terminal is the canonical setup.
- Codex: cloud tasks turn a description into a pull request; the local CLI runs the same loop in your terminal.
- Cursor: vibe coding inside an editor, where the code stays on screen even if you don't read it.

## In conversation

> “I vibe coded the whole dashboard on Saturday and it works. Should I put it in front of customers?”
>
> “Now the stakes changed. Keep the loop, but add tests, get a review, and read the auth code yourself.”

**Related:** [One-shot](./one-shot.md) · [Prototyping](./prototyping.md) · [AFK](./afk.md) · [Harness](./harness.md)

## Learn it in the school

- [Course 01 · Vibe Coding using Claude Code](https://vibecodeschool.com/courses/claude-code-vibe-coding)
- [Course 01 · The Agentic Loop](https://vibecodeschool.com/learn/cc-04-the-agentic-loop)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/vibe-coding) · added 2026-09-12
