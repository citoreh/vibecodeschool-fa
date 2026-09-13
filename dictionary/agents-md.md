<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# AGENTS.md

> The instructions file at the repo root that every session reads first: commands, conventions, gotchas. CLAUDE.md in Claude Code.

*§06 Memory & Steering · also called: CLAUDE.md, Rules file, .cursorrules, Instructions file, GEMINI.md · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/agents-md)*

AGENTS.md is a plain Markdown file at the root of a repository that a coding [agent](./agent.md) loads whenever a [session](./session.md) begins. It is the standing brief for the codebase: how to run the tests, which package manager to use, the conventions that matter, and the traps that have bitten before. Codex and a growing list of tools read `AGENTS.md`; Claude Code reads `CLAUDE.md`; Cursor keeps rules in a `.cursor/rules` directory. Same idea, different filename.

Because it is loaded every session, it is the cheapest way to fix a repeated mistake and the easiest file to bloat. Every line costs [context](./context.md) on every request, and a file that grows into a full architecture guide starts crowding out the task. The other failure is silence: no file at all, so each session guesses the build command, guesses the style, and re-learns the same lesson you taught it last week.

Keep it short and operational. Commands first, then conventions, then gotchas, each as a line or two. For anything longer, point to a document instead of pasting it, and let [progressive disclosure](./progressive-disclosure.md) do the rest: the agent reads the deep doc only when the task needs it. Update it when the agent gets something wrong twice. It works alongside the [system prompt](./system-prompt.md), which the [harness](./harness.md) controls, and the [memory system](./memory-system.md), which holds facts the agent writes for itself.

## In the tools

- Claude Code: `CLAUDE.md` at the repo root, optional ones in subdirectories, and a personal one under `~/.claude/`; `/init` drafts a first version.
- Codex: reads `AGENTS.md` from your home directory, the repo root, and nested directories, merged with the nearest file taking precedence.
- Cursor: `.cursor/rules/*.mdc` files, scoped by glob so a rule only loads for matching paths; the legacy `.cursorrules` still works.

## In conversation

> “Every session it runs npm test and the suite is under pnpm. I'm tired of correcting it.”
>
> “Put it in AGENTS.md. One line: 'Use pnpm; run tests with pnpm test.'”
>
> “That's all?”
>
> “That's all. It's loaded with every new session, so you never have to say it twice.”

**Related:** [Context engineering](./context-engineering.md) · [Skill](./skill.md) · [Slash command](./slash-command.md)

## Learn it in the school

- [Course 01 · CLAUDE.md and Project Memory](https://vibecodeschool.com/learn/cc-05-claude-md-and-memory)
- [Course 03 · Knowledge: Teaching Antigravity Your Codebase](https://vibecodeschool.com/learn/ag-10-when-to-add-specialist)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/agents-md) · added 2026-09-12
