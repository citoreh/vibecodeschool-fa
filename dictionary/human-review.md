<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Human review

> A person reading the agent's work before it ships. The only step that judges whether the change is right, not just whether it passes.

*§07 Patterns of Work · also called: Code review, Diff review · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/human-review)*

Human review is you, or a teammate, reading what the [agent](./agent.md) produced and deciding whether it ships. It is the last stage of the loop and the only one that can answer the questions the machine can't: is this the feature we meant, is the design sane, would I be comfortable maintaining this, does it do anything the [spec](./spec.md) didn't ask for?

The pressure to skip it is real. An agent produces more code than you can comfortably read, the [checks](./automated-check.md) are green, and the diff looks plausible. That's exactly when unreviewed work leaks into production: an agent that quietly widened a permission, deleted a test that was 'flaky', or added a dependency to make a problem go away. The failures of [vibe coding](./vibe-coding.md) are almost always failures of review, not of generation.

Make review cheap enough to actually do. Ask for small pull requests, one concern each. Read the tests first, because they state what the agent believed the task was. Let an [automated review](./automated-review.md) pass flag the mechanical issues so your attention goes to intent and design. And when the diff is too big to review, that's a signal to split the task, not to skim.

## In the tools

- GitHub: the pull request is the standard review surface; branch protection can require a human approval before merge.
- Antigravity: a review policy can route every merge through a person even when the agents run unattended.
- Cursor and Claude Code: the inline diff view lets you accept or reject each edit as it lands.

## In conversation

> “Green checks, bot review is clean, can I just merge it?”
>
> “Read the tests it wrote first. If they match what we asked for, skim the rest. If they don't, the code doesn't matter.”

**Related:** [Human-in-the-loop](./human-in-the-loop.md) · [AFK](./afk.md) · [Handoff artifact](./handoff-artifact.md)

## Learn it in the school

- [Course 01 · Code Review with Claude](https://vibecodeschool.com/learn/cc-21-code-review)
- [Course 03 · Ship It: Branches, PRs, and the Human Merge](https://vibecodeschool.com/learn/ag-09-deployer-agents)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/human-review) · added 2026-09-12
