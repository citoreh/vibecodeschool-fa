<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Headless mode

> Running the agent from a script or CI with a prompt and no interactive UI; the result comes back as text or JSON.

*§03 Tools & Environment · also called: Non-interactive mode, Print mode, Scripted run, -p · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/headless-mode)*

Headless mode runs the [agent](./agent.md) without its interactive interface: you pass a prompt on the command line or from a script, the agent does the work, and the result comes back as plain text or JSON on stdout. Nobody types, nobody clicks. Claude Code does this with `claude -p 'your prompt'`, Codex with `codex exec`, and most harnesses have an equivalent. It is the same loop, same [model](./model.md), same [tools](./tool.md), just driven by a program instead of a person.

Headless is how the agent becomes a building block. A CI job that reviews every pull request, a nightly run that updates docs to match the code, a script that fans a hundred repos through the same migration, a scheduled routine that refreshes a dataset: each is an agent invoked headlessly with a fixed prompt. The trade is that nothing can be asked mid-run. A [permission request](./permission-request.md) with no one to answer it either blocks forever or has to be pre-decided, so the [permission mode](./permission-mode.md) must be set in advance.

Treat a headless run like any unattended automation. Run it in a [sandbox](./sandbox.md) or a clean checkout, cap its budget and time, make its output machine-checkable (JSON with a schema beats prose), and end in something reviewable such as a PR or a report rather than a direct change. Log the [tool calls](./tool-call.md) so a bad run can be diagnosed. Everything that applies to [AFK](./afk.md) work applies twice here, because you may not even be awake.

## In the tools

- Claude Code: `claude -p 'prompt'` prints the result; `--output-format json` makes it parseable and `--allowedTools` fixes permissions up front.
- Codex: `codex exec` runs non-interactively with the sandbox and approval policy given as flags.
- Claude Cowork and ChatGPT Work: scheduled tasks are the no-code cousin, a saved prompt run on a timer with the result delivered to you.

## In conversation

> “Can we get a first-pass review on every PR before a human looks?”
>
> “Yes, run it headless in CI: pipe the diff to the agent with the review prompt, post the JSON findings as a comment.”
>
> “Read-only tools only, and it never approves anything itself.”

**Related:** [Automated review](./automated-review.md) · [Hooks](./hooks.md) · [Worktree](./worktree.md) · [Usage limit](./usage-limit.md)

## Learn it in the school

- [Course 03 · Auto-PR Pipeline](https://vibecodeschool.com/learn/ag-21-auto-pr-pipeline)
- [Course 06 · Scheduled Tasks](https://vibecodeschool.com/learn/cw-14-scheduled-tasks)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/headless-mode) · added 2026-09-12
