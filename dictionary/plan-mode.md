<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Plan mode

> A read-only agent mode: the agent may search and read, but must propose a plan for your approval before it edits anything.

*§03 Tools & Environment · also called: Planning mode, Read-only mode, Ask mode · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/plan-mode)*

Plan mode is an [agent mode](./agent-mode.md) in which the [agent](./agent.md) can read files, search the codebase and run harmless commands, but cannot edit or execute anything that changes state. Its job is to come back with a plan: which files it will touch, in what order, what it is unsure about, and how it will verify the result. You read the plan, correct it, and only then switch to an editing mode. The [permission mode](./permission-mode.md) underneath is 'ask for everything that mutates', with a system-prompt nudge to investigate first.

A wrong plan is cheap. A wrong implementation is not: by the time you notice, the agent has changed fifteen files, the tests are green for the wrong reasons, and unpicking it costs more than starting over. Plan mode moves the correction to the point where it is a sentence instead of a revert. It also surfaces the assumptions the agent would otherwise silently make about your codebase, which is where most [AFK](./afk.md) runs go wrong.

Use it for anything bigger than a one-file change, and pair it with a written [spec](./spec.md) so the plan has something to be checked against. A plan that survives a round of [grilling](./grilling.md) becomes a good [handoff artifact](./handoff-artifact.md): save it to a file, start a fresh session, and let that session execute with the sharp end of its [context window](./context-window.md) free for the work. Skip plan mode for trivial edits; the overhead isn't worth it there.

## In the tools

- Claude Code: Shift+Tab into plan mode, or the agent can enter it itself when a task looks large; leaving the mode asks you to approve the plan.
- Cursor: the Plan option in the agent panel drafts a step list you can edit before running.
- Codex: there is no single plan toggle; ask for a plan explicitly, or use a read-only sandbox for the same effect.

## In conversation

> “Before you let it loose on the auth refactor, what did the plan say?”
>
> “Plan mode found that sessions are also written by the cron job, which I'd forgotten. It wants to change both. Good catch, approved.”
>
> “That's the sort of thing you'd only have found after the tests broke.”

**Related:** [Steering](./steering.md) · [Checkpoint](./checkpoint.md) · [Design concept](./design-concept.md)

## Learn it in the school

- [Course 01 · Plan Mode](https://vibecodeschool.com/learn/cc-15-plan-mode)
- [Course 01 · Spec → Tests → Code](https://vibecodeschool.com/learn/cc-18-spec-tests-code)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/plan-mode) · added 2026-09-12
