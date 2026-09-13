<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Primary source

> The real thing: the file, the diff, the test output, the docs page. What the agent should read instead of a description of it.

*§05 Handoffs · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/primary-source)*

A primary source is the original material itself: the actual file on disk, the failing test's output, the API's own documentation, the commit diff. It stands opposite to a [secondary source](./secondary-source.md), which is someone's account of that material, including the [agent](./agent.md)'s own earlier summary of it. When the agent reads a primary source, what lands in [context](./context.md) is the truth as of right now, not a recollection of it.

Agents drift when they work from descriptions. You tell it the endpoint returns a list, it builds around a list, and the endpoint has returned a paginated object since March. Or a [handoff artifact](./handoff-artifact.md) says the tests pass, the new session trusts that, and builds on a broken base. Every layer of retelling loses detail, and the model fills the gaps with [parametric knowledge](./parametric-knowledge.md) that may be out of date.

Point the agent at sources, not summaries. Instead of explaining what a function does, say “read `lib/auth.ts` before you change the login flow.” When a library is newer than the model's [knowledge cutoff](./knowledge-cutoff.md), have it fetch the current docs rather than guess. When a handoff makes a claim, verify it against the repo before trusting it. This is cheap: a [tool call](./tool-call.md) costs less than a wrong assumption.

## In the tools

- Claude Code: the Read tool and `@file` mentions pull primary sources into context; WebFetch does the same for docs.
- Cursor: `@file` and `@docs` references attach the source itself rather than your paraphrase of it.
- Most tools: pasting a URL is not the same as fetching it; check that the agent actually read the page.

## In conversation

> “I told it the config lives in settings.json and it still wrote to the wrong path.”
>
> “Did it read the file, or just your description of it?”
>
> “My description.”
>
> “Have it open the actual file. The primary source beats anything either of you remembers.”

**Related:** [Contextual knowledge](./contextual-knowledge.md) · [Hallucination](./hallucination.md) · [Grilling](./grilling.md)

## Learn it in the school

- [Course 01 · Reading and Editing Files](https://vibecodeschool.com/learn/cc-06-reading-and-editing)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/primary-source) · added 2026-09-12
