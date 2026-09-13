<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Harness engineering

> Improving the setup around the model (tools, checks, instructions, permissions) so the same model does better work.

*§07 Patterns of Work · also called: Environment engineering, Agent ops · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/harness-engineering)*

Harness engineering is the practice of improving everything around the [model](./model.md) instead of the prompt: the tools it can call, the [permission mode](./permission-mode.md), the [hooks](./hooks.md) that run after each edit, the [automated checks](./automated-check.md), the instructions in [AGENTS.md](./agents-md.md), the sandbox it runs in. The [harness](./harness.md) is what turns a model into an [agent](./agent.md); engineering it is how you get better work out of a model you can't change.

Most complaints that 'the model got dumber' are harness problems in disguise. The agent can't find the test command, so it stops running tests. It doesn't know the repo conventions, so it invents its own. Its tool list is thirty MCP servers wide, so it picks the wrong one. Each is fixable in the setup, and none is fixable by a longer prompt in the next session.

The loop is simple. Watch where the agent stumbles, ask which missing tool, check or instruction would have prevented it, add that, re-run. Keep a log of stumbles for a week and the priorities write themselves. Done consistently, this is what people mean by good [AX](./ax.md): an environment where an agent can look around, verify its own work, and be told the rules once.

## In the tools

- Claude Code: hooks, permission rules, custom slash commands, skills and CLAUDE.md are the main harness levers; the sandbox is another.
- Antigravity: knowledge items, review policies and workspace setup are the same levers at fleet scale.
- Cursor: rules files and MCP configuration are where most of the harness lives.

## In conversation

> “Every session it forgets to run the linter before committing.”
>
> “Stop reminding it. Put the lint command in a post-edit hook and a line in AGENTS.md. That's harness engineering, not prompting.”

**Related:** [MCP](./mcp.md) · [Context engineering](./context-engineering.md) · [Sandbox](./sandbox.md) · [Skill](./skill.md)

## Learn it in the school

- [Course 01 · Hooks: Pre and Post Tool](https://vibecodeschool.com/learn/cc-16-hooks)
- [Course 03 · Knowledge: Teaching Antigravity Your Codebase](https://vibecodeschool.com/learn/ag-10-when-to-add-specialist)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/harness-engineering) · added 2026-09-12
