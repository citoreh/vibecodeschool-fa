<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Agent mode

> A named preset that bundles a permission mode with behavioural instructions, switchable in the middle of a session.

*§03 Tools & Environment · also called: Mode · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/agent-mode)*

An agent mode is a preset the [harness](./harness.md) offers that changes two things at once: the [permission mode](./permission-mode.md) (what can run without asking) and a slice of the [system prompt](./system-prompt.md) (how the [agent](./agent.md) is told to behave). 'Plan' modes forbid edits and instruct the model to investigate and propose. 'Accept edits' modes let file changes flow but still gate commands. 'Ask' or 'chat' modes turn the agent into a consultant that touches nothing. You can flip between them inside one [session](./session.md) without losing context.

Modes are worth understanding because the same [model](./model.md) behaves noticeably differently under each, and people blame the model. An agent that 'refuses to make changes' is often just sitting in a read-only mode. An agent that 'went rogue and edited twelve files' was in an auto-accept mode you toggled earlier and forgot about. The mode indicator in the UI is the first thing to check when behaviour seems off.

A good rhythm uses modes deliberately: start a task in [plan mode](./plan-mode.md) to align on the approach, switch to an editing mode to execute, and drop back to a read-only mode to review. Treat the mode switch as part of the [steering](./steering.md) vocabulary, alongside interrupting and re-prompting.

## In the tools

- Claude Code: Shift+Tab cycles default, accept edits and plan; the current mode is shown next to the input.
- Cursor: Agent, Ask and Plan are selectable in the chat panel and set what the assistant may touch.
- Codex: the mode is expressed as an approval policy plus sandbox settings rather than a single named toggle.

## In conversation

> “It wrote a beautiful plan and then just stopped.”
>
> “You're in plan mode. That's the deal: it plans, you approve, then you switch modes and it builds.”
>
> “Ah. Shift+Tab, then.”

**Related:** [Permission request](./permission-request.md) · [Headless mode](./headless-mode.md) · [Hooks](./hooks.md)

## Learn it in the school

- [Course 01 · Plan Mode](https://vibecodeschool.com/learn/cc-15-plan-mode)
- [Course 03 · Autonomy and Review Policies](https://vibecodeschool.com/learn/ag-05-approval-gates)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/agent-mode) · added 2026-09-12
