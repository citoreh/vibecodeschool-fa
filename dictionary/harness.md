<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Harness

> The software around the model that gives it hands: a system prompt, tools, permissions, hooks and the loop that feeds results back.

*§01 The Model · also called: Agent harness, Scaffold · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/harness)*

A harness is the software that wraps a [model](./model.md) and gives it hands. It writes the [system prompt](./system-prompt.md), defines the [tools](./tool.md), executes each tool call and feeds the [tool result](./tool-result.md) back in, asks before risky actions, decides when a long [session](./session.md) gets compacted, and loads project instructions such as [AGENTS.md](./agents-md.md). Claude Code, Codex, Cursor's agent and Antigravity's manager are all harnesses; the model is one component inside each.

Most of what you experience as the agent's personality is harness behaviour. One product asks before every shell command and another just runs it; one rewrites whole files and another edits by diff; one remembers your preferences and another forgets them at restart. Same underlying model, different wrapper. When a run goes sideways, look at the wrapper before you blame the weights.

It's also where your leverage lives. You can't change the model, but you can change nearly everything the harness does: add tools through [MCP](./mcp.md), set hooks that run your linter after every edit, tighten or loosen the [permission mode](./permission-mode.md), write skills, shape the memory files. Treating the harness as configurable infrastructure rather than a black box is the difference between using an agent and running one.

**Avoid:** 'The AI' as a catch-all when what you mean is the harness. Naming the wrapper tells you where to look, and it's where most fixes live.

## In the tools

- Claude Code: the harness is the CLI, its settings files, hooks and MCP config; the model is whatever `/model` currently says.
- Antigravity: the agent manager is a harness that runs several agents, each with its own workspace and review policy.

## In conversation

> “Claude in the browser explains the bug perfectly but Claude Code keeps missing it.”
>
> “Different harness. The CLI is working from your actual files and tests; give it the same context you pasted into chat and it'll get there.”

**Related:** [Agent](./agent.md) · [Harness engineering](./harness-engineering.md) · [Environment](./environment.md)

## Learn it in the school

- [Course 01 · The Agentic Loop](https://vibecodeschool.com/learn/cc-04-the-agentic-loop)
- [Course 01 · Hooks: Pre and Post Tool](https://vibecodeschool.com/learn/cc-16-hooks)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/harness) · added 2026-09-12
