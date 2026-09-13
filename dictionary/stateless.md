<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Stateless

> Nothing carries over on its own: each model request starts from zero, and each new session does too.

*§02 Sessions, Context Windows & Turns · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/stateless)*

A stateless system keeps nothing between calls. The model behind your coding agent is stateless in the strictest sense: every request it answers is a fresh computation over whatever text arrives with it, and when the response is finished, nothing is retained. The 'conversation' you see in Claude Code or Codex is not the model remembering. It is the [harness](./harness.md) resending the whole transcript on every [model provider request](./model-provider-request.md).

The same is true one level up. By default an [agent](./agent.md) is stateless across [sessions](./session.md): close the terminal and the instructions you gave, the files it inspected and the decisions you made together are gone. The felt version is opening a new session, asking it to 'continue', and watching it re-explore the repo from scratch or break a rule you set an hour ago.

Nothing is broken here; this is the baseline you build on. Anything you want to survive has to be written down where the next session will read it: an [AGENTS.md](./agents-md.md) file, a [memory system](./memory-system.md), or a [handoff artifact](./handoff-artifact.md). Treat the model as an excellent colleague with total amnesia, and keep the durable state in files.

## In the tools

- Claude Code: the transcript is resent on every request; `claude --continue` or `--resume` reloads a saved transcript rather than restoring any model memory.
- Most tools: 'memory' features are files or notes the harness re-injects into context; the model itself never remembers anything.

## In conversation

> “It fixed the linting rule yesterday. Why is it breaking it again today?”
>
> “New session, new context. The model is stateless, and so is the session unless you write the rule into CLAUDE.md.”

**Related:** [Stateful](./stateful.md) · [Context window](./context-window.md) · [Clearing](./clearing.md)

## Learn it in the school

- [Course 01 · CLAUDE.md and Project Memory](https://vibecodeschool.com/learn/cc-05-claude-md-and-memory)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/stateless) · added 2026-09-12
