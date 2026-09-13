<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Automated review

> A model reads the agent's diff and flags problems before a person does: judgement without a human, fuzzier than a check.

*§07 Patterns of Work · also called: AI code review, Agent review · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/automated-review)*

Automated review is a model reviewing the work of a model. A separate [session](./session.md), often a [subagent](./subagent.md) or a bot on the pull request, reads the diff with fresh [context](./context.md) and reports what looks wrong: a missed edge case, a security smell, a change that doesn't match the [spec](./spec.md). It sits between an [automated check](./automated-check.md), which is exact but narrow, and [human review](./human-review.md), which is expensive but has taste.

The reason to use a fresh reviewer rather than asking the same session to check itself is [sycophancy](./sycophancy.md) plus contamination. The session that wrote the code carries every assumption that produced the bug, so it tends to confirm its own work. A reviewer that only sees the diff and the requirements has none of that baggage and catches things the author can't.

Treat its output as a triage list, not a verdict. Point the reviewer at specific concerns (correctness, security, the acceptance criteria in the ticket) instead of asking for a general opinion, and have it verify each finding by reading the surrounding code before reporting. Anything flagged with evidence goes back to the author session as a fix; anything vague gets ignored. It reduces what a human has to read; it doesn't replace the human.

## In the tools

- Claude Code: a `/code-review` pass reviews the current diff; a reviewer subagent with a narrow brief does the same on demand.
- GitHub: Copilot review and similar bots comment on pull requests automatically; Vercel Agent does the same for Vercel projects.

## In conversation

> “The review bot left fourteen comments on a forty-line PR.”
>
> “Half are style. Tell the automated review to only flag correctness and security, and to cite the line that proves it.”

**Related:** [Grilling](./grilling.md) · [AFK](./afk.md) · [Harness engineering](./harness-engineering.md)

## Learn it in the school

- [Course 01 · Code Review with Claude](https://vibecodeschool.com/learn/cc-21-code-review)
- [Course 03 · Second Opinions](https://vibecodeschool.com/learn/ag-13-voting-and-consensus)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/automated-review) · added 2026-09-12
