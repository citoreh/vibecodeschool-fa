<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Autocompact

> Compaction the harness triggers on its own when the context window nears its limit, without asking you first.

*§05 Handoffs · also called: Auto-compaction, Automatic compaction · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/autocompact)*

Autocompact is [compaction](./compaction.md) that the [harness](./harness.md) performs automatically when the [context window](./context-window.md) gets close to full. You do not ask for it; the harness notices the session is near the limit, summarizes the history, and carries on. Claude Code shows a warning as the threshold approaches and a notice when it happens. The point is to keep a long [session](./session.md) running instead of stopping it with an error.

Because it fires on a size threshold rather than a task boundary, it tends to land at the worst moment: halfway through a multi-file change, with the plan half in the [agent](./agent.md)'s head. The agent continues from a summary it did not choose the timing of, and the drop in quality can look like the model suddenly getting worse. People often blame the model when the real event was an autocompact three [turns](./turn.md) ago.

Do not let it be a surprise. Watch the context indicator and compact or [clear](./clearing.md) on your own terms before the harness does it for you. Keep state on disk, in commits, notes, and a [handoff artifact](./handoff-artifact.md), so a summary is never the only copy of anything. If your sessions autocompact regularly, the tasks are too big for one session; split them into [tickets](./ticket.md).

## In the tools

- Claude Code: autocompact is on by default and warns as context fills; you can turn it off in `/config` and run `/compact` by hand.
- Codex: the CLI compacts long threads automatically as well; a new task is often the cleaner move.

## In conversation

> “It was doing great and then suddenly started renaming things it had already renamed.”
>
> “Check the transcript. Did the context get compacted a few turns back?”
>
> “Yes, there's a notice I didn't see.”
>
> “That's your culprit. Next time compact yourself before it hits the threshold, and write the file list down first.”

**Related:** [Smart zone](./smart-zone.md) · [Attention degradation](./attention-degradation.md) · [Checkpoint](./checkpoint.md)

## Learn it in the school

- [Course 01 · When to Interrupt vs Let It Run](https://vibecodeschool.com/learn/cc-20-when-to-interrupt)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/autocompact) · added 2026-09-12
