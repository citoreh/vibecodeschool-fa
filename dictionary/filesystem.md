<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Filesystem

> The directory tree the agent reads, edits and runs inside; for a coding agent, the main part of the environment.

*§03 Tools & Environment · also called: File system, Working directory · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/filesystem)*

The filesystem is the directory tree the agent can see: the repo you launched it in, its files, and usually its parent folders if you let it wander. For a coding [agent](./agent.md), this is most of its [environment](./environment.md). Reading a file, editing a file, listing a directory and searching for a string are all [tool calls](./tool-call.md) against the filesystem, and the [results](./tool-result.md) are the agent's only view of your code.

Two things follow. First, the agent only knows what it has read. A 4,000-file monorepo is not 'in' the [context window](./context-window.md); the handful of files the agent chose to open are. When it edits a function without opening the callers, the callers were simply never in its world. Second, anything on disk is fair game as input: a stray `.env`, a giant `node_modules` folder, an old TODO file. Search tools will find them and the agent may act on them.

Keep the tree tidy where it matters. A clear folder layout and a short [AGENTS.md](./agents-md.md) pointing at the right entry points do more than any clever prompt. Ignore files (`.gitignore`, plus tool-specific ignore lists) keep build output and secrets out of searches. When you launch the agent, launch it from the directory you actually want it to treat as the world, not from your home folder.

## In the tools

- Claude Code: file tools are scoped to the launch directory by default, and it asks before touching paths outside it.
- Cursor: `.cursorignore` hides paths from indexing and search; most other harnesses lean on `.gitignore` for the same job.
- Claude Cowork: the filesystem is only the folders you explicitly share with it.

## In conversation

> “Why did it rewrite the API client in packages/legacy? Nobody uses that.”
>
> “Search matched there first, so that's the file it read. It has no idea which package is live unless something in the filesystem says so.”
>
> “Adding a one-line README to legacy and an ignore rule for it now.”

**Related:** [Worktree](./worktree.md) · [Sandbox](./sandbox.md) · [Context](./context.md) · [Checkpoint](./checkpoint.md)

## Learn it in the school

- [Course 01 · Reading and Editing Files](https://vibecodeschool.com/learn/cc-06-reading-and-editing)
- [Course 01 · Searching the Codebase](https://vibecodeschool.com/learn/cc-07-searching-the-codebase)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/filesystem) · added 2026-09-12
