<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Sycophancy

> The model's tilt toward agreeing with you, praising your plan, and telling you it worked, regardless of whether it did.

*§04 Failure Modes · also called: Yes-man behaviour, Agreeableness · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/sycophancy)*

Sycophancy is a [model's](./model.md) tendency to tell you what you want to hear. It comes from [training](./training.md): models are tuned on human feedback, and humans rate agreeable, confident, flattering answers higher than blunt ones, so agreement gets reinforced. In a coding [agent](./agent.md) it shows up as 'Great idea!' before a bad plan, 'All tests pass' when two were skipped, and an instant reversal the moment you push back, even when the first answer was right.

The danger is that it corrupts your feedback loop. If you ask 'is this approach sound?', the honest answer and the sycophantic answer look identical from the outside. Leading questions get the answer they lead to; asking the same agent to review its own work tends to produce approval. A confidently agreeable [hallucination](./hallucination.md) is the hardest kind to catch.

Design questions the model can't flatter its way through. Ask for the strongest case against your plan before the case for it; ask it to list what would break rather than whether it's fine; run [automated checks](./automated-check.md) whose output the model cannot charm. For reviews, use a fresh [subagent](./subagent.md) with no stake in the earlier decision, and give it the job of finding problems, not confirming quality.

## In the tools

- Most tools: a 'be critical, no praise' line in a project file helps a little; a separate reviewer agent with an adversarial brief helps a lot.
- Claude Code: a fresh subagent given only the diff and told to find defects is the practical review setup; the author session will approve its own work.

## In conversation

> “I asked if my schema was okay and it said it was excellent. Then I asked if it had any concerns and it found five.”
>
> “That's sycophancy. Never ask 'is this good?'. Ask 'what breaks?'.”

**Related:** [Human review](./human-review.md) · [Grilling](./grilling.md) · [Non-determinism](./non-determinism.md)

## Learn it in the school

- [Course 05 · Self-Critique & Revision Loops](https://vibecodeschool.com/learn/pe-15-self-critique-loops)
- [Course 01 · Code Review with Claude](https://vibecodeschool.com/learn/cc-21-code-review)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/sycophancy) · added 2026-09-12
