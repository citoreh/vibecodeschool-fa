<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Tool

> A named capability the harness lets the model invoke, such as reading a file, running a shell command or fetching a page.

*§03 Tools & Environment · also called: Function, Built-in tool · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/tool)*

A tool is a named capability the [harness](./harness.md) offers the [model](./model.md): read this file, run this command, search for this pattern, fetch this URL. Each one comes with a description and a parameter schema, and the whole list travels with every [model provider request](./model-provider-request.md). When the model wants to use one, it writes a [tool call](./tool-call.md) as text; the harness runs the underlying code and hands back a [tool result](./tool-result.md). Nothing runs inside the model. Execution is the harness's job.

The tool list is the agent's reach. A shell tool alone covers most of what a developer does at a keyboard, which is why so much agent work flows through it, and why it deserves the tightest permissions. Take a tool away and the agent doesn't complain, it improvises: with no browser tool it will guess what a page looks like, with no test runner it will 'reason about' whether tests pass. Missing tools produce fabrication, not errors.

Tools have a standing cost too. Every definition takes up [context](./context.md) on every request, and a long list of overlapping tools makes the model pick the wrong one more often. Add tools deliberately: one per capability the task genuinely needs, with a description that says when to use it. [MCP](./mcp.md) is how you plug in tools the harness doesn't ship with.

## In the tools

- Claude Code: ships with Read, Edit, Write, Bash, Glob, Grep, WebFetch and an Agent tool for subagents; MCP servers add more.
- Codex: a similar core set around a sandboxed shell; tools show up as commands the app asks you to approve.
- Cursor: tools live behind the editor's agent panel, including terminal, file edits and web search.

## In conversation

> “It keeps saying the Figma export looks right, but it can't open Figma.”
>
> “Right, there's no tool for it. Without one, the model fills the gap with a plausible description instead of a look.”
>
> “So either we give it a screenshot tool or we stop asking it about visuals.”

**Related:** [Environment](./environment.md) · [Permission request](./permission-request.md) · [Skill](./skill.md)

## Learn it in the school

- [Course 01 · The Agentic Loop](https://vibecodeschool.com/learn/cc-04-the-agentic-loop)
- [Course 04 · Function Calling & Structured Outputs](https://vibecodeschool.com/learn/aa-03-function-calling-structured-outputs)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/tool) · added 2026-09-12
