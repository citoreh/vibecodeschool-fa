<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# One-shot

> Getting a usable result from a single prompt with no follow-up turns. A good test of a prompt, a bad habit for production.

*§07 Patterns of Work · also called: One-shotting, One-shot prompt, Zero-shot build · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/one-shot)*

One-shotting a task means the first prompt produces the finished thing: no clarifying questions, no second [turn](./turn.md), no 'actually, also…'. It is a claim about the prompt and the task together. The prompt was complete enough, and the task small and well-trodden enough, that the [agent](./agent.md) could go from description to working result without you in the loop.

Don't confuse it with the prompt-engineering meaning, where one-shot means a prompt that includes exactly one worked example (next to zero-shot and few-shot). In agentic coding the word is about the number of rounds, not the number of examples. When someone says a feature 'one-shotted', they mean it landed on the first try.

What makes a prompt one-shottable is that it reads like a [spec](./spec.md): the stack, the files to touch, the acceptance criteria, the constraints, the things not to do. Vague prompts get a plausible guess; complete prompts get the thing. That makes one-shot a useful benchmark for your prompting (the 'Can I Vibe Code It?' prompts on this site are written to be one-shottable) and a poor default for real work, where iterating with [human review](./human-review.md) between rounds catches what a single pass can't. One-shot the small, boring pieces; iterate on the ones that matter.

## In the tools

- Most tools: the same prompt one-shots more often in a fresh session with a clean context than deep into a long one.
- Claude Code: an approved plan from plan mode followed by a single execution prompt often one-shots a medium-sized feature.

## In conversation

> “I pasted the prompt from the site and it one-shotted the whole app.”
>
> “Nice. Now change one thing and watch what breaks. One-shot gets you a starting point, not a finished product.”

**Related:** [Vibe coding](./vibe-coding.md) · [Prototyping](./prototyping.md) · [Context engineering](./context-engineering.md) · [Grilling](./grilling.md)

## Learn it in the school

- [Course 05 · Zero-Shot, One-Shot, Few-Shot](https://vibecodeschool.com/learn/pe-05-zero-one-few-shot)
- [Course 01 · Spec → Tests → Code](https://vibecodeschool.com/learn/cc-18-spec-tests-code)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/one-shot) · added 2026-09-12
