<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Subagent

> A separate agent the main agent spins up for a bounded task, with its own context window; only its final report comes back.

*§06 Memory & Steering · also called: Sub-agent, Agent tool, Child agent · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/subagent)*

A subagent is an [agent](./agent.md) launched by another agent to handle a bounded piece of work. It runs with its own [context window](./context-window.md), often its own [system prompt](./system-prompt.md) and [tool](./tool.md) list, does the job, and returns a short report. The parent never sees the subagent's intermediate steps: the twenty file reads, the failed searches, the log dumps all stay in the child's window and are discarded when it finishes. Only the conclusion crosses back.

This is mostly a [context engineering](./context-engineering.md) tool. A search across a large repo can pull thousands of lines into [context](./context.md); done in a subagent, the parent pays for a paragraph. It also enables parallelism, with several subagents working different parts of a task at once. The costs are real too: each subagent starts from zero, so it needs a self-contained brief, and it cannot see what the parent has already learned unless the parent tells it.

Delegate work whose output is a conclusion, not a conversation: research, broad searches, independent reviews, isolated implementation in a [worktree](./worktree.md). Write the brief as if for a new hire with no history, including what done looks like. Keep tight, sequential edits in the main session where the state lives. Verify what comes back: a subagent can be confidently wrong, and the parent has no transcript to check, only the report.

## In the tools

- Claude Code: the Agent tool launches subagents; custom ones are defined in `.claude/agents/` with their own prompt, tools, and model.
- Antigravity: the agent manager runs multiple agents across workspaces; each is effectively a subagent you supervise from the inbox.
- Codex: cloud tasks can be fanned out as parallel runs; each run is isolated like a subagent.

## In conversation

> “The main session is bloating every time it searches the monorepo.”
>
> “Push the search into a subagent. It reads everything, you get back the six files that matter.”
>
> “Does it know what we've decided so far?”
>
> “Only what's in the brief. Give it the question and the constraints, nothing else needed.”

**Related:** [AFK](./afk.md) · [Handoff artifact](./handoff-artifact.md) · [Sandbox](./sandbox.md)

## Learn it in the school

- [Course 01 · Subagents and the Agent Tool](https://vibecodeschool.com/learn/cc-14-subagents)
- [Course 03 · Parallel Agents Across Workspaces](https://vibecodeschool.com/learn/ag-12-fan-out-fan-in)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/subagent) · added 2026-09-12
