<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# System prompt

> The standing instructions the harness puts in front of every request: who the agent is, what tools it has, how it should behave.

*§02 Sessions, Context Windows & Turns · also called: System message · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/system-prompt)*

The system prompt is the block of instructions the [harness](./harness.md) places at the top of every [model provider request](./model-provider-request.md), ahead of your messages. It tells the [model](./model.md) what role it is playing, which [tools](./tool.md) exist and how to call them, what the house rules are and, in coding agents, a good deal about how to work: when to ask, how to format edits, what to check before declaring a task done. You rarely see it, but the model sees it first on every single turn.

Because it is resent each time and sits at the front of the [context](./context.md), the system prompt has outsized influence, and it explains a lot of behaviour that looks like the model's personality. Claude Code asking before a destructive command, Codex writing a summary at the end of a task, Cursor preferring small diffs: those are harness instructions. When two products on the same model behave differently, the system prompt is usually the first place the difference lives.

You do not edit the vendor's system prompt, but you extend it. Project instruction files such as [AGENTS.md](./agents-md.md) and CLAUDE.md are appended into the same request, which is why a rule written there feels 'built in' while a rule typed in chat fades as the session grows. Keep those files short and specific; they cost [input tokens](./input-tokens.md) on every request, and a bloated one dilutes its own rules.

## In the tools

- Claude Code: CLAUDE.md files (global, project and local) are folded into the system-level instructions on every request.
- Anthropic API: the `system` parameter sets the prompt directly; a harness is just the layer that writes it for you.

## In conversation

> “Why does it always run the linter after editing, even when I didn't ask?”
>
> “That's in the system prompt, or in the CLAUDE.md that gets appended to it. Change the instruction there rather than fighting it every turn.”

**Related:** [Prompt injection](./prompt-injection.md) · [Steering](./steering.md) · [Prefix cache](./prefix-cache.md)

## Learn it in the school

- [Course 05 · Anatomy of a Prompt](https://vibecodeschool.com/learn/pe-02-anatomy-of-a-prompt)
- [Course 01 · CLAUDE.md and Project Memory](https://vibecodeschool.com/learn/cc-05-claude-md-and-memory)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/system-prompt) · added 2026-09-12
