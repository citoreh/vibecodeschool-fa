<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Agent

> A model wired to tools and a loop: it reads, acts, checks the result, and goes again until the task is done or you stop it.

*§02 Sessions, Context Windows & Turns · also called: Coding agent, AI agent · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/agent)*

An agent is a [model](./model.md) put to work inside a loop. The [harness](./harness.md) gives it a [system prompt](./system-prompt.md), a set of [tools](./tool.md) and a task; the model decides on an action, the harness carries it out and returns the result, and the model decides again. Claude Code, Codex, Cursor's agent mode and Antigravity's managed agents are all this same shape, with different tools, defaults and interfaces wrapped around it.

What separates an agent from a chat window is that it can act on the world and observe the consequences. A chat assistant can tell you how to fix the test; an agent runs the test, reads the failure, edits the file and runs it again. That loop is where the leverage comes from, and also where the risk comes from: a wrong assumption made early gets executed, not just described.

The practical skill is directing the loop, not replacing it. Give the agent a clear target and a way to verify it (a failing test, a command that must pass), decide how much autonomy to grant through its [permission mode](./permission-mode.md), and review what comes back. If you want to understand why one agent behaves differently from another running the same model, look at the harness, not the weights.

## In the tools

- Claude Code: Anthropic's terminal agent; Bash, file edits, search and subagents are its core tools.
- Codex: OpenAI's agent, available as a CLI, an IDE extension and cloud tasks that run in isolated containers.
- Antigravity: Google's editor where a manager view runs several agents in parallel across workspaces.

## In conversation

> “It ran the tests, saw two failures, fixed both, and reran them before I'd even read the first error.”
>
> “That's the agent loop doing its job. Your part is deciding what 'done' means before it starts.”

**Related:** [Turn](./turn.md) · [Subagent](./subagent.md) · [Agent mode](./agent-mode.md) · [Human-in-the-loop](./human-in-the-loop.md)

## Learn it in the school

- [Course 01 · The Agentic Loop](https://vibecodeschool.com/learn/cc-04-the-agentic-loop)
- [Course 04 · What Makes a System Agentic](https://vibecodeschool.com/learn/aa-10-what-makes-a-system-agentic)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/agent) · added 2026-09-12
