<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Design concept

> A short written description of what you're building and why, agreed before any code, so the agent and you share the same picture.

*§07 Patterns of Work · also called: Design brief, Concept doc · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/design-concept)*

A design concept is the one-page answer to 'what are we building and why?', written down before implementation starts. It names the user, the problem, the shape of the solution and the things that are deliberately out of scope. It is looser than a [spec](./spec.md), which says exactly what to build, and more concrete than an idea, which lives only in your head.

Agents make the missing concept expensive. Give an [agent](./agent.md) a feature request with no concept behind it and it will invent one: it decides who the user is, what 'done' means and which trade-offs matter, silently, in the first few minutes, and every later decision compounds on that guess. The output can be polished and still solve the wrong problem.

Write the concept with the agent, not for it. A [grilling](./grilling.md) session is the fastest way: let the model interview you until the fuzzy parts are resolved, then ask it to write the concept back to you in a page. That page becomes a [handoff artifact](./handoff-artifact.md) that a fresh [session](./session.md) can pick up, and the source the spec and the [tickets](./ticket.md) are derived from. If you can't write the concept, you're not ready to prompt.

## In the tools

- Claude Code: plan mode is a natural place to draft a concept, since the agent can read the repo but can't edit until you approve.
- Claude Cowork and ChatGPT Work: a concept doc is the kind of artifact these tools produce well from a short conversation.

## In conversation

> “I have the feature idea. Should I just start prompting?”
>
> “Write the design concept first, even if it's ten lines. Otherwise the agent decides what the feature is and you find out in the PR.”

**Related:** [Prototyping](./prototyping.md) · [Primary source](./primary-source.md) · [Context pointer](./context-pointer.md) · [Plan mode](./plan-mode.md)

## Learn it in the school

- [Course 01 · Spec → Tests → Code](https://vibecodeschool.com/learn/cc-18-spec-tests-code)
- [Course 03 · Plans and Task Lists](https://vibecodeschool.com/learn/ag-06-planner-agents)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/design-concept) · added 2026-09-12
