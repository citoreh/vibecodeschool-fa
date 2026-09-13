<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Sandbox

> An isolated place for the agent to run, such as a container, VM or restricted shell, so a bad action can't reach the rest of your machine.

*§03 Tools & Environment · also called: Sandboxing, Isolated environment · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/sandbox)*

A sandbox is a walled-off [environment](./environment.md) for the [agent](./agent.md): a container, a virtual machine, a cloud session, or a shell whose filesystem and network access are restricted. Whatever the agent does in there stays in there. It can delete files, install packages and run scripts, and the worst case is a fresh sandbox rather than a lost afternoon. The [harness](./harness.md) still executes [tool calls](./tool-call.md) normally; the walls are around the process, not inside the [model](./model.md).

Sandboxing is what makes permissive [permission modes](./permission-mode.md) reasonable. Without it, 'bypass permissions' means trusting a non-deterministic text generator with your home directory, your SSH keys and every credential in your shell. With it, the same setting is just a way to stop babysitting. The common mistake is a leaky sandbox: a container that mounts your real repo read-write and inherits your environment variables has walls with a door propped open.

Decide what the sandbox must not reach, then verify it can't. Production credentials, package publishing tokens and cloud accounts stay outside. Give the agent a copy or a [worktree](./worktree.md) of the code, a scratch database, and network access only to what the task needs. For parallel [AFK](./afk.md) runs, one sandbox per agent keeps them from stepping on each other. Cloud-hosted agent sessions are sandboxes someone else maintains, which is most of their appeal.

## In the tools

- Claude Code: cloud sessions run in a fresh container per session; locally, an optional sandbox restricts filesystem and network access for Bash.
- Codex: runs commands inside an OS-level sandbox by default, with network off unless you allow it.
- Antigravity: each agent works in its own workspace, and security policies control what it may reach.

## In conversation

> “I want three agents chewing through the migration backlog overnight.”
>
> “Then put each one in its own sandbox with a throwaway database. Permissions wide open inside, no prod access, PRs at the end.”
>
> “And the sandbox dies when the run ends?”

**Related:** [Headless mode](./headless-mode.md) · [Checkpoint](./checkpoint.md) · [Hooks](./hooks.md) · [AX](./ax.md)

## Learn it in the school

- [Course 03 · Security and Sandboxing](https://vibecodeschool.com/learn/ag-19-security)
- [Course 06 · Cloud Sessions and Your Phone](https://vibecodeschool.com/learn/cw-13-cloud-sessions-and-mobile)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/sandbox) · added 2026-09-12
