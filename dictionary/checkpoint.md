<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Checkpoint

> A saved state of your files, and sometimes the conversation, that you can rewind to after a turn goes wrong.

*§03 Tools & Environment · also called: Rewind, Snapshot, Restore point · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/checkpoint)*

A checkpoint is a saved snapshot of the working tree, and in some harnesses the conversation too, that you can return to. Before the [agent](./agent.md) starts a [turn](./turn.md) the [harness](./harness.md) records what the files looked like; if the turn goes badly, you rewind and the edits vanish. It is the undo button for agentic work, where a single turn can touch dozens of files and Ctrl+Z in the editor is no longer enough.

The need shows up the first time an agent 'fixes' something by rewriting half a module. Reviewing the diff, you realise the earlier state was better, but the earlier state is gone, spread across twenty edits. Git would have saved you, if you had committed. Most people hadn't, because they were in the middle of something. Harness checkpoints fill exactly that gap between commits. One subtlety: rewinding the files without rewinding the conversation leaves the agent believing its edits still exist, and its next [tool call](./tool-call.md) will act on a world that isn't there. Rewind both, or tell it what you did.

Make checkpoints boring. Commit before every substantial agent run so there is a known-good state to diff against, even if the message is just 'wip before refactor'. Use the harness's rewind for the small stuff between commits, and `git stash` or a [worktree](./worktree.md) when you want to try two approaches side by side. A [sandbox](./sandbox.md) plus a clean commit is the checkpoint that never fails.

## In the tools

- Claude Code: press Esc twice (or use `/rewind`) to pick an earlier point; you can restore the code, the conversation, or both.
- Cursor: each agent message carries a restore control that returns the files to that point.
- Most tools: where no built-in rewind exists, a commit before the run and `git restore .` afterwards does the same job.

## In conversation

> “That last turn made things worse. Can I get back to where we were five minutes ago?”
>
> “Rewind to the checkpoint before it started, then re-prompt with the constraint it missed.”
>
> “And rewind the conversation too, or it'll think the broken version is still on disk.”

**Related:** [Permission request](./permission-request.md) · [Steering](./steering.md) · [AFK](./afk.md)

## Learn it in the school

- [Course 01 · Git Operations and Commits](https://vibecodeschool.com/learn/cc-09-git-and-commits)
- [Course 03 · Stopping, Steering, and Retrying](https://vibecodeschool.com/learn/ag-14-cancellation-retries)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/checkpoint) · added 2026-09-12
