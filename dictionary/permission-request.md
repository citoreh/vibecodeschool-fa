<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Permission request

> The harness pausing before a risky tool call to ask you yes or no; the simplest human-in-the-loop gate there is.

*§03 Tools & Environment · also called: Approval prompt, Permission prompt · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/permission-request)*

A permission request is the [harness](./harness.md) stopping before a [tool call](./tool-call.md) and asking you to approve it. The [model](./model.md) has already decided what it wants to do (edit this file, run this command, hit this URL); the request shows you the exact action and waits. Approve and the call runs; deny and the model gets a [tool result](./tool-result.md) saying it was refused, and usually tries another route. Which calls trigger a request is set by the [permission mode](./permission-mode.md).

This is the cheapest [human-in-the-loop](./human-in-the-loop.md) mechanism there is, and also the easiest to wear out. Early in a project you read every prompt carefully. Forty prompts later you are hitting Enter without looking, which is exactly when the agent runs the migration against the wrong database. Approval fatigue turns a safety feature into a ritual. The opposite failure is also common: a session left running [AFK](./afk.md) sits on a permission request for an hour because nobody was there to answer.

Use requests for the calls that are genuinely hard to undo, and pre-approve the rest. Most harnesses let you allowlist specific commands (`npm test`, `git status`, formatters) and specific paths so that routine work flows and only the dangerous calls stop you. For unattended runs, decide up front: either run in a [sandbox](./sandbox.md) with broad permissions, or restrict the agent to actions that don't need asking.

## In the tools

- Claude Code: requests appear inline with yes, yes-and-don't-ask-again, or no; `/permissions` manages the allow and deny lists.
- Codex: commands outside the sandbox raise an approval in the thread; the approval policy sets how often that happens.
- Claude Cowork: file writes and connector actions surface as approvals in the task view.

## In conversation

> “It stopped again. It wants to run rm -rf dist.”
>
> “That's the permission request doing its job. Approve it once, then allowlist that exact command if it's part of the build.”
>
> “And keep the prompt for anything touching .env?”

**Related:** [Agent mode](./agent-mode.md) · [Hooks](./hooks.md) · [Checkpoint](./checkpoint.md)

## Learn it in the school

- [Course 01 · When to Interrupt vs Let It Run](https://vibecodeschool.com/learn/cc-20-when-to-interrupt)
- [Course 06 · The Approval Loop](https://vibecodeschool.com/learn/cw-04-the-approval-loop)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/permission-request) · added 2026-09-12
