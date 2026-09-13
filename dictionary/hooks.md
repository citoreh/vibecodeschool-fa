<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Hooks

> Commands you configure the harness to run at fixed moments, such as before or after a tool call, regardless of what the model wants.

*§03 Tools & Environment · also called: Lifecycle hooks, Pre-tool hook, Post-tool hook · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/hooks)*

Hooks are commands you configure the [harness](./harness.md) to run at fixed points in the loop: before a [tool call](./tool-call.md), after one, when the [session](./session.md) starts or ends, when the [agent](./agent.md) is about to stop, or when it needs your attention. They are plain shell commands or scripts, and they run whether or not the [model](./model.md) would have chosen to. A hook can also block: a pre-tool hook that exits with an error prevents the call from happening at all.

The reason hooks exist is that instructions are advisory. You can write 'always run the formatter after editing' in [AGENTS.md](./agents-md.md) and the agent will do it most of the time; on a long turn deep in the [dumb zone](./smart-zone.md), it will forget. A post-edit hook that runs Prettier never forgets. The same goes for guardrails: a hook that rejects any command containing `rm -rf` or a push to `main` is a rule the agent literally cannot talk its way past.

Use hooks for the things that must happen every time and are cheap to check mechanically: formatting, linting, running the affected tests, blocking dangerous commands, logging every call for audit. Keep them fast; a slow hook taxes every tool call. And keep the nuanced judgment in instructions and [skills](./skill.md) where the model can weigh it, because a hook has no judgment at all, which is exactly its value.

## In the tools

- Claude Code: hooks are configured in settings under events such as PreToolUse, PostToolUse, Stop and Notification, with matchers for specific tools.
- Most tools: where a harness has no hook system, a git pre-commit hook or a CI check gives you the after-the-fact half of the same protection.

## In conversation

> “It committed unformatted code again, even though CLAUDE.md says to format first.”
>
> “Stop asking. Add a post-edit hook that runs the formatter on the changed file, and the question goes away.”
>
> “And a pre-commit hook that fails if the tests don't pass?”

**Related:** [Automated check](./automated-check.md) · [Permission request](./permission-request.md) · [Harness engineering](./harness-engineering.md)

## Learn it in the school

- [Course 01 · Hooks: Pre and Post Tool](https://vibecodeschool.com/learn/cc-16-hooks)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/hooks) · added 2026-09-12
