<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Turn

> Your message and all the work the agent does before it hands control back to you.

*§02 Sessions, Context Windows & Turns · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/turn)*

A turn is the unit of back-and-forth in a [session](./session.md): you say something, the [agent](./agent.md) works until it has nothing more to do without you, and control comes back. From your side that is one exchange. Underneath, a single turn can contain many [model provider requests](./model-provider-request.md), because after every [tool call](./tool-call.md) the harness feeds the result to the model and asks what comes next. A turn that reads eight files and runs the tests twice is a dozen round trips billed as one conversation step.

This is the mismatch behind surprising bills and slow responses. The cost of a turn is not the length of your message; it is how many tool calls the agent needs and how much [context](./context.md) gets resent on each of them. Late in a long session every request carries the whole transcript, so the same simple turn costs several times what it cost at the start.

Shorter, more decisive turns tend to work better than sprawling ones. Give the agent a bounded task, let the turn run, review, then take the next turn with what you learned. If a turn is heading somewhere wrong, interrupt it (see [steering](./steering.md)) rather than letting it complete a plan you already know is off.

## In the tools

- Claude Code: a turn ends when the agent stops and the prompt returns; Escape interrupts a running turn.
- Antigravity: the manager view shows each agent's turns as steps you can inspect and approve individually.

## In conversation

> “That one turn took four minutes and cost more than my whole morning.”
>
> “It made about thirty tool calls, and each one resends the context. Late-session turns are expensive; compact or start fresh.”

**Related:** [Output tokens](./output-tokens.md) · [Human-in-the-loop](./human-in-the-loop.md) · [Automated check](./automated-check.md)

## Learn it in the school

- [Course 01 · The Agentic Loop](https://vibecodeschool.com/learn/cc-04-the-agentic-loop)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/turn) · added 2026-09-12
