<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Permission mode

> The setting that decides which tool calls run automatically and which stop for a permission request.

*§03 Tools & Environment · also called: Auto-approve, Bypass permissions, YOLO mode, Full-auto · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/permission-mode)*

Permission mode is the rule the [harness](./harness.md) applies to every [tool call](./tool-call.md) before running it: execute silently, or stop and raise a [permission request](./permission-request.md). It ranges from cautious (ask about every edit and every command) through allowlists (routine commands run, unusual ones ask) to fully automatic (nothing asks). The [model](./model.md) doesn't change; what changes is how much can happen between your glances at the screen.

The mode shapes the work more than people expect. In a strict mode the [agent](./agent.md) moves in short hops and you stay in the loop by default. In a permissive mode it can complete a whole feature while you get coffee, and it can also delete a directory, push to the wrong branch, or run a script that phones home. 'YOLO mode' is the community name for the fully automatic end for a reason. The danger isn't the mode itself, it is running it outside a [sandbox](./sandbox.md) on a machine that holds things you care about.

Match the mode to the blast radius. Interactive work on a real checkout: allowlist the safe commands and keep asking for the rest. Unattended or parallel runs: go permissive, but inside a container, a [worktree](./worktree.md) or a cloud session with no production credentials, and end in a PR rather than a merge. And read the diff afterwards regardless; permissions gate actions, they don't check quality.

## In the tools

- Claude Code: Shift+Tab cycles the interactive modes (default, accept edits, plan); `--dangerously-skip-permissions` is the fully automatic one.
- Codex: an approval policy plus a sandbox level (read-only, workspace-write, full access) do the same job; the older suggest / auto-edit / full-auto names still circulate.
- Antigravity: autonomy and review policies set how much an agent can do before a human checks in.

## In conversation

> “Can I just turn permissions off? The prompts are killing my flow.”
>
> “In a sandboxed worktree, sure. On your main checkout with prod keys in .env, no. Allowlist the build and test commands instead.”
>
> “Fair. Allowlist for the daily stuff, bypass only in the container.”

**Related:** [Agent mode](./agent-mode.md) · [AFK](./afk.md) · [Headless mode](./headless-mode.md) · [Hooks](./hooks.md)

## Learn it in the school

- [Course 03 · Autonomy and Review Policies](https://vibecodeschool.com/learn/ag-05-approval-gates)
- [Course 01 · When to Interrupt vs Let It Run](https://vibecodeschool.com/learn/cc-20-when-to-interrupt)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/permission-mode) · added 2026-09-12
