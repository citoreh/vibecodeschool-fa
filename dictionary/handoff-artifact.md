<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Handoff artifact

> The written note that carries a task across a session boundary: what's done, what's left, what was decided, where to look.

*§05 Handoffs · also called: Handoff doc, Handoff note · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/handoff-artifact)*

A handoff artifact is the document a [session](./session.md) leaves behind so the next session can continue the work. It is the concrete half of a [handoff](./handoff.md): a file in the repo, a pull request description, a comment on a [ticket](./ticket.md), or a note in a scratch directory. A good one answers four questions: what was done, what remains, what was decided and why, and which files, commands, or logs to read first.

Weak artifacts are either too vague (“made progress on auth”) or too long, dumping the whole conversation into a file the next session has to wade through. Both fail for the same reason: the reader cannot tell what matters. And an artifact written from memory at the end of a tired session often records what the [agent](./agent.md) believes happened rather than what the diff shows.

Ask the agent to write the artifact while the session still has [context](./context.md), and have it cite [primary sources](./primary-source.md): file paths, test names, commit hashes. Keep it short enough to read in a minute. Store it where the next session will naturally find it, such as a `HANDOFF.md` next to the code or the PR body itself. The next session's first job is to read it, then verify the claims against the repo before building on them.

## In the tools

- Claude Code: have the agent write the note to a file, then `/clear`; the next session reads it with one Read call.
- Antigravity: the walkthrough and task list an agent produces double as the handoff artifact for review.
- Codex: the PR description Codex writes for a cloud task is the artifact; tighten it before you merge.

## In conversation

> “Before you stop, write the handoff.”
>
> “Sure. What goes in it?”
>
> “Done, remaining, decisions with reasons, and the three files to read first. Paths, not descriptions.”
>
> “Committed as HANDOFF.md. Tests green as of that commit.”

**Related:** [Spec](./spec.md) · [Compaction](./compaction.md) · [Checkpoint](./checkpoint.md)

## Learn it in the school

- [Course 01 · Git Operations and Commits](https://vibecodeschool.com/learn/cc-09-git-and-commits)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/handoff-artifact) · added 2026-09-12
