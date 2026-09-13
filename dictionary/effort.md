<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Effort

> How hard the model thinks before replying. Turn it up for tricky problems and pay in tokens and wait; turn it down for routine edits.

*§01 The Model · also called: Reasoning effort, Extended thinking, Thinking budget, Ultrathink · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/effort)*

Effort sets how much private thinking a [model](./model.md) is allowed before it commits to an answer. At higher settings the model writes out a longer chain of intermediate thinking, checks itself, and explores alternatives before producing the visible reply. Those thinking tokens are [output tokens](./output-tokens.md), so higher effort costs more money and more wall-clock time per [model provider request](./model-provider-request.md).

The trade-off is real in both directions. Low effort on a tricky refactor produces confident, fast, wrong code. High effort on 'rename this variable' burns a minute and a pile of tokens for a change that needed none. Much of what people report as 'the model is dumb today' or 'the model is slow today' is an effort setting that doesn't match the task.

Match effort to the job. Planning (in [plan mode](./plan-mode.md) or on paper), debugging a subtle failure, and anything touching concurrency or security deserve high effort. Mechanical edits, formatting and boilerplate don't. Many harnesses let you flip it per request rather than per session, so the habit is: raise it when you're about to ask something hard, then drop it back down.

## In the tools

- Claude Code: extended thinking is triggered per request; phrases like 'think hard' raise the thinking budget, and newer models expose an effort level directly.
- Codex: `model_reasoning_effort` in the config sets low, medium or high; you can also change it from the model picker.
- Cursor: reasoning-capable models appear as separate 'thinking' variants or a thinking toggle in the model list.

## In conversation

> “It's been thinking for two minutes on a one-line change.”
>
> “Drop the effort. Save the high setting for the migration plan, not for renaming a prop.”

**Related:** [Inference](./inference.md) · [Usage limit](./usage-limit.md) · [Grilling](./grilling.md)

## Learn it in the school

- [Course 05 · Reasoning Models vs CoT Prompts](https://vibecodeschool.com/learn/pe-12-reasoning-models-vs-cot)
- [Course 04 · Latency, Cost & Reliability Budgets](https://vibecodeschool.com/learn/aa-05-latency-cost-reliability)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/effort) · added 2026-09-12
