<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# AX

> Agent experience: how well a codebase, tool or environment supports an agent that starts each session knowing nothing.

*§07 Patterns of Work · also called: Agent experience · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/ax)*

AX, agent experience, is [DX](./dx.md) with an [agent](./agent.md) as the user. It asks how easily an agent that starts with an empty [context](./context.md) can orient itself, find the right command, verify its own work and stay within the rules of the codebase. Where DX is about a person's day, AX is about a [session](./session.md): everything the agent needs has to be discoverable from inside the [environment](./environment.md), because there is no osmosis and no colleague to ask.

Poor AX looks like an agent that is capable in general and clumsy in your repo. It runs the wrong package manager, misses the tests that live in an unusual folder, reinvents a helper that already exists, or ships a change that violates a rule everyone on the team knows and nobody wrote down. The fix is rarely a better model; it's usually a better environment.

The tools of AX are ordinary: an [AGENTS.md](./agents-md.md) file that states the commands and conventions, [automated checks](./automated-check.md) that fail loudly and fast, tools that reach the systems the task touches, and a repo layout that makes the important things findable. Treat every stumble in an [AFK](./afk.md) run as an AX bug and fix the environment rather than the prompt. Because the agent is the only one there for most of the run, AX is the support it gets.

## In the tools

- Claude Code: CLAUDE.md, hooks and skills are the main AX surface; `/init` drafts a first CLAUDE.md from the repo.
- Antigravity: knowledge items teach the agents your codebase once and reuse it across the fleet.
- GitHub: a clear README, scripts in package.json and CI that mirrors the local checks all raise AX for cloud agents.

## In conversation

> “It spent twenty minutes trying to figure out how we run migrations.”
>
> “That's an AX problem. One line in AGENTS.md and a `make migrate` target, and it never happens again.”

**Related:** [Harness engineering](./harness-engineering.md) · [Hooks](./hooks.md) · [Skill](./skill.md) · [Tool](./tool.md)

## Learn it in the school

- [Course 01 · CLAUDE.md and Project Memory](https://vibecodeschool.com/learn/cc-05-claude-md-and-memory)
- [Course 03 · Knowledge: Teaching Antigravity Your Codebase](https://vibecodeschool.com/learn/ag-10-when-to-add-specialist)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/ax) · added 2026-09-12
