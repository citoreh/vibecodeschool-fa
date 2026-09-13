<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Human-in-the-loop

> A working pattern where a person approves, corrects, or answers for the agent while it runs, instead of only judging the result.

*§07 Patterns of Work · also called: HITL, Supervised run · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/human-in-the-loop)*

Human-in-the-loop means a person stays part of the run: the [agent](./agent.md) pauses for a [permission request](./permission-request.md), asks a question when the task is ambiguous, or waits for an answer before it commits to a direction. The human is a step in the loop, not just a reader of the output at the end. In most coding harnesses this is the default: the agent proposes an edit or a command, you approve or redirect, it continues.

The trade-off is throughput for control. Every pause costs your attention, and if you rubber-stamp fifty prompts in a row you get the cost of supervision without the benefit. The opposite failure is just as common: leaving the loop for an hour and coming back to polished work that took a turn you'd have stopped had you been watching.

Use it deliberately. Stay in the loop when the task touches money, data, other people's systems, or anything you can't roll back; keep the interruptions meaningful by pre-approving the safe, boring [tool calls](./tool-call.md) in your [permission mode](./permission-mode.md). Move toward [AFK](./afk.md) runs only once [automated checks](./automated-check.md) can catch what you would have caught by watching.

## In the tools

- Claude Code: the default permission mode asks before edits and shell commands, and the agent can pause mid-task to ask you a question.
- Antigravity: review policies decide which agent actions land in your inbox for approval and which run straight through.
- Claude Cowork: file changes and external actions go through an approval step unless you widen it.

## In conversation

> “Why does it keep stopping to ask me about every shell command?”
>
> “That's human-in-the-loop doing its job. Allow the read-only stuff, keep the approvals for anything that writes or deploys.”

**Related:** [Steering](./steering.md) · [Human review](./human-review.md) · [Agent mode](./agent-mode.md) · [Sandbox](./sandbox.md)

## Learn it in the school

- [Course 06 · The Approval Loop](https://vibecodeschool.com/learn/cw-04-the-approval-loop)
- [Course 03 · Autonomy and Review Policies](https://vibecodeschool.com/learn/ag-05-approval-gates)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/human-in-the-loop) · added 2026-09-12
