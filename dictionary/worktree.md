<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Worktree

> A second checkout of the same git repo in its own directory, so an agent can work on a branch without touching yours.

*§03 Tools & Environment · also called: Git worktree, Parallel checkout · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/worktree)*

A worktree is an extra checkout of a git repository in a separate directory, sharing the same `.git` history but sitting on its own branch. `git worktree add ../feature-x feature-x` gives you a second working copy where a change can be made, built and tested without disturbing the files in your main checkout. For an [agent](./agent.md), a worktree is a private [filesystem](./filesystem.md) to work in while you keep using yours.

The problem it solves shows up the first time you run two things at once. You start an agent on a refactor, then open the same repo to fix a bug; the agent's half-finished edits are in your editor, your fix lands in its [context](./context.md) mid-task, and both of you end up confused about which files are whose. Branch switching doesn't help, because a switch rewrites the very files the agent is editing. Separate directories do.

Give each parallel task its own worktree, especially for [AFK](./afk.md) runs, and treat a worktree like a [sandbox](./sandbox.md) with the code already inside. Remember they cost disk space and a fresh dependency install each, so prune finished ones (`git worktree remove`) and commit or discard the work before you do. Some harnesses create and clean up worktrees for you per task; that is the same mechanism with the housekeeping automated.

## In the tools

- Claude Code: subagents can be given an isolated worktree that is cleaned up if nothing changed, and the CLI can drop you into one for a task.
- Antigravity: parallel agents run in separate workspaces by design; the manager view shows each one's branch.
- Most tools: a plain `git worktree add` works with any harness, since a worktree is just a directory.

## In conversation

> “Can I keep coding while it does the i18n sweep? That touches every screen.”
>
> “Run it in a worktree. It gets its own copy on its own branch, you stay on main, and you merge when it's done.”
>
> “So no more 'why is my file changing while I type' moments.”

**Related:** [Checkpoint](./checkpoint.md) · [Subagent](./subagent.md) · [Headless mode](./headless-mode.md)

## Learn it in the school

- [Course 03 · Parallel Agents Across Workspaces](https://vibecodeschool.com/learn/ag-12-fan-out-fan-in)
- [Course 01 · Git Operations and Commits](https://vibecodeschool.com/learn/cc-09-git-and-commits)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/worktree) · added 2026-09-12
