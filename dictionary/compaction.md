<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Compaction

> Replacing the session so far with a shorter summary of it, freeing the context window at the cost of detail.

*§05 Handoffs · also called: /compact, Context summarization · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/compaction)*

Compaction shrinks a [session](./session.md) by replacing its history with a summary. The [harness](./harness.md) asks the [model](./model.md) to condense everything so far, throws away the original messages and [tool results](./tool-result.md), and continues with the summary in their place. The [context window](./context-window.md) gets room back; what you keep is a [secondary source](./secondary-source.md) account of what happened rather than the record itself. In Claude Code the manual command is `/compact`.

The cost is silent. The summary keeps what the model judged important, which is not always what you will need next. A constraint you mentioned once, a file path, the exact error text, the reason a fix was rejected: any of them can vanish, and the agent that continues has no idea it is missing something. The first few [turns](./turn.md) after compaction are where confident mistakes cluster.

Compact deliberately, at a natural boundary, and tell the harness what to preserve: “keep the list of files changed and the failing test names.” Better still, write the important state to disk first so it survives regardless. If the summary would need to carry a lot, that is a sign to write a [handoff artifact](./handoff-artifact.md) and use [clearing](./clearing.md) instead. Compaction is a bridge, not a memory system.

## In the tools

- Claude Code: `/compact` accepts instructions, e.g. `/compact keep the migration checklist`; the summary replaces the transcript.
- Codex: the CLI has its own `/compact`; treat it the same way and start a new task when a summary would lose too much.
- Most tools: after any compaction, re-read the files you care about rather than trusting the summary.

## In conversation

> “Context is at ninety percent and I'm mid-refactor.”
>
> “Compact it, but tell it what to keep: the module list and the test that's still red.”
>
> “Won't it forget the API constraint?”
>
> “It might. Put that line in the repo notes before you compact, then it can't.”

**Related:** [Autocompact](./autocompact.md) · [Attention degradation](./attention-degradation.md) · [Smart zone](./smart-zone.md) · [Primary source](./primary-source.md)

## Learn it in the school

- [Course 01 · When to Interrupt vs Let It Run](https://vibecodeschool.com/learn/cc-20-when-to-interrupt)
- [Course 05 · Long-Context Prompting](https://vibecodeschool.com/learn/pe-20-long-context-prompting)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/compaction) · added 2026-09-12
