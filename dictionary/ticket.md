<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Ticket

> A bounded unit of work with a clear done state, sized so an agent can finish it in one session.

*§05 Handoffs · also called: Issue, Task · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/ticket)*

A ticket is one bounded piece of work: a title, enough description to act on, and a definition of done. Issue trackers have used the word for decades; in agentic coding it takes on a second meaning as the natural unit you hand an [agent](./agent.md). A ticket is smaller than a [spec](./spec.md) and larger than a single prompt. It should fit inside one [session](./session.md) with room to spare.

Tickets that are too big are the common failure. “Migrate the app to the new auth provider” sounds like a task, but it is a project, and an agent given a project will run until it drifts out of the [smart zone](./smart-zone.md), then keep going anyway. Tickets that are too vague fail differently: the agent picks an interpretation and builds it, and you find out at review time.

Slice work into tickets that end in something checkable: a passing test, a green [automated check](./automated-check.md), a screen you can open. Put the acceptance criteria in the ticket itself, so the same text works as the prompt, the [handoff artifact](./handoff-artifact.md), and the review checklist. When an agent runs [AFK](./afk.md), one ticket per run keeps failures small and diffs reviewable.

## In the tools

- Codex: cloud tasks are ticket-shaped by design; one task, one sandbox, one pull request.
- Claude Code: paste the ticket as the first message, or point the agent at the GitHub issue with `gh issue view`.
- Antigravity: the manager breaks a request into tasks; keep each one ticket-sized before you approve the plan.

## In conversation

> “Can I give it the whole redesign in one go?”
>
> “Split it into tickets first. One screen, one ticket, each with a done condition.”
>
> “That's like twelve runs.”
>
> “Twelve reviewable PRs instead of one you can't read. That's the point.”

**Related:** [One-shot](./one-shot.md) · [Human review](./human-review.md) · [Worktree](./worktree.md)

## Learn it in the school

- [Course 03 · Plans and Task Lists](https://vibecodeschool.com/learn/ag-06-planner-agents)
- [Course 01 · Building a Next.js Feature](https://vibecodeschool.com/learn/cc-23-nextjs-feature)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/ticket) · added 2026-09-12
