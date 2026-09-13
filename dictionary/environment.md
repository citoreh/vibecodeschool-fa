<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Environment

> Everything outside the harness the agent can inspect or change: your repo, your shell, the services it can reach, the browser it drives.

*§03 Tools & Environment · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/environment)*

The environment is the world an [agent](./agent.md) works in: the repository on disk, the shell it runs commands in, the databases and APIs it can reach, the browser it can drive. The [model](./model.md) never touches any of it directly. It learns about the environment through [tool results](./tool-result.md) and changes it through [tool calls](./tool-call.md), so the environment is exactly as large as the set of [tools](./tool.md) the [harness](./harness.md) exposes.

This is why an agent can be brilliant in one repo and lost in another. A broken environment reads as a stupid model. If tests can't run because a dependency is missing, if the shell has no network, if the staging URL needs a login the agent doesn't have, the agent will still try to finish the task, and it will guess about the parts it can't see. The output is confident, coherent, and wrong about the world.

Treat the environment as part of the prompt. Before a long run, check that the commands the agent will need actually work from a fresh shell: install, test, lint, build. Give it the same access you would give a new teammate on day one, and put the things it can't see into files it can read. Most of what people call [AX](./ax.md) is just making the environment legible.

## In the tools

- Claude Code: the environment is your current directory plus whatever your shell can reach; cloud sessions get a fresh container with the repo cloned in.
- Antigravity: each agent gets its own workspace, and the browser tool extends the environment to whatever the agent can open.
- Claude Cowork: the environment is the folders you grant plus connectors such as Gmail and Calendar, rather than a repo.

## In conversation

> “It says the migration passed, but staging is still on the old schema.”
>
> “It never touched staging. Nothing in its environment can reach that database, so it ran the migration locally and reported that.”
>
> “So I either give it a tool for staging, or tell it to stop at a PR.”

**Related:** [Filesystem](./filesystem.md) · [Sandbox](./sandbox.md) · [MCP](./mcp.md) · [Worktree](./worktree.md)

## Learn it in the school

- [Course 01 · Install the CLI](https://vibecodeschool.com/learn/cc-02-install-the-cli)
- [Course 03 · Security and Sandboxing](https://vibecodeschool.com/learn/ag-19-security)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/environment) · added 2026-09-12
