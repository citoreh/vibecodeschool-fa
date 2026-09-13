<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# DX

> Developer experience: how pleasant and fast a tool, codebase or workflow is for the humans using it.

*§07 Patterns of Work · also called: Developer experience · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/dx)*

DX, developer experience, is the quality of a developer's day: how quickly a tool gets out of the way, how readable the errors are, how fast the feedback loop runs, how much of the setup is remembered for you. It is a design goal for tools, libraries and codebases alike, and for years it was the main lens for judging whether a workflow was any good.

AI coding adds a second lens. A codebase can have great DX and still be hostile to an [agent](./agent.md): conventions that live in people's heads, a test suite that needs a running database nobody documented, a monorepo where the right command depends on which folder you're in. Humans absorb those by osmosis. An agent starts every [session](./session.md) knowing none of it and has to be told, or it guesses.

In practice the two pull the same direction more often than not. Fast tests, clear errors, one command to run everything and written conventions are good for people and essential for agents. When you invest in DX now, ask the second question too: could an agent with a clean [context](./context.md) and the tools in this repo do the task? That question has its own name, [AX](./ax.md), and it is where the next round of leverage lives.

## In the tools

- Most tools: fast type-checking, a single test command and readable errors improve DX and the agent's success rate at the same time.

## In conversation

> “Our DX is great, everyone loves the codebase. Why does the agent keep breaking it?”
>
> “Because everything it needs to know is in your heads. Write it down and the DX becomes AX.”

**Related:** [Harness engineering](./harness-engineering.md) · [AGENTS.md](./agents-md.md) · [Automated check](./automated-check.md) · [Environment](./environment.md)

## Learn it in the school

- [Course 01 · CLAUDE.md and Project Memory](https://vibecodeschool.com/learn/cc-05-claude-md-and-memory)
- [Course 03 · Measuring Your Agent Leverage](https://vibecodeschool.com/learn/ag-20-slas)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/dx) · added 2026-09-12
