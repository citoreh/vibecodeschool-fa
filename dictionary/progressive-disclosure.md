<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Progressive disclosure

> Giving the agent a short index up front and letting it load the detail only when a task calls for it.

*§06 Memory & Steering · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/progressive-disclosure)*

Progressive disclosure is the practice of exposing information in layers: a brief summary that is always present, with the full material available on request. In an agent setting, the top layer lives in [AGENTS.md](./agents-md.md) or a [skill](./skill.md)'s description and costs a few lines of [context](./context.md). The lower layers are files, docs, and tools the [agent](./agent.md) reads only when the task turns out to need them. The name comes from interface design, where menus hide advanced options until you ask.

The alternative is loading everything up front, which fails in two directions. The [context window](./context-window.md) fills with material the task never touches, and the [attention budget](./attention-budget.md) that should go to the task is spread across pages of irrelevant setup. Sessions that start slow and sloppy often have a thousand-line instructions file as the cause, not the [model](./model.md).

Structure your instructions as a map, not a manual. The always-loaded file says what exists and when to read it: “deployment steps are in docs/deploy.md; read it before touching infra.” That line is a [context pointer](./context-pointer.md). Skills work the same way, with a one-line description in the index and the full procedure loaded on invocation. The agent stays sharp because it only pays for what it uses.

## In the tools

- Claude Code: skills expose only their name and description until invoked; the SKILL.md body loads on use.
- Claude Cowork: skills and connectors appear as short descriptions and expand only when the task calls for them.
- Most tools: nested instruction files in subdirectories are a form of it; they load when the agent works in that directory.

## In conversation

> “Should I put the whole API style guide in CLAUDE.md?”
>
> “No. One line saying where it is and when to read it. That's progressive disclosure.”
>
> “What if it doesn't read it?”
>
> “Then say 'read docs/api-style.md before adding endpoints.' The pointer is cheap; the guide only loads when it's needed.”

**Related:** [Context engineering](./context-engineering.md) · [Smart zone](./smart-zone.md) · [MCP](./mcp.md)

## Learn it in the school

- [Course 01 · Agent Skills](https://vibecodeschool.com/learn/cc-28-agent-skills)
- [Course 04 · Context Engineering](https://vibecodeschool.com/learn/aa-06-context-engineering)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/progressive-disclosure) · added 2026-09-12
