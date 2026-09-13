<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# AI

> An umbrella word that keeps changing what it points at. In coding today it means a language model plus the harness that lets it act.

*§01 The Model · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/ai)*

AI is an umbrella word, not a specific technology. Right now, when someone in a coding context says 'the AI', they almost always mean a large language [model](./model.md) wrapped in a [harness](./harness.md) that lets it read files, run commands and edit code. Ten years ago the same word pointed at recommendation systems and image classifiers; ten years from now it will point at something else. The label follows the frontier.

The vagueness costs you when you're debugging. 'The AI got it wrong' doesn't tell you whether the model produced a bad [next-token prediction](./next-token-prediction.md), the harness fed it a bloated [context window](./context-window.md), a [tool call](./tool-call.md) failed silently, or your prompt was ambiguous. Each of those has a different fix, and the word AI hides which one you're looking at.

The habit worth building is to swap the umbrella word for the specific part. Say model when you mean the trained network, [agent](./agent.md) when you mean the model plus its loop, harness when you mean the product around it (Claude Code, Codex, Cursor). The rest of this dictionary exists so you have those words ready.

## In the tools

- Claude Code: the model is Claude; the harness is the CLI around it. Most 'AI' complaints turn out to be about one or the other.
- Cursor: 'AI' covers autocomplete, chat and the agent, which are three different harness features over similar models.

## In conversation

> “My AI keeps rewriting the whole file instead of the one function.”
>
> “Which part? The model, or Claude Code's edit tool? If the tool is doing full-file writes, that's a harness setting, not a model problem.”

**Related:** [Model provider](./model-provider.md) · [Vibe coding](./vibe-coding.md) · [Parametric knowledge](./parametric-knowledge.md)

## Learn it in the school

- [Course 04 · How LLMs Actually Work](https://vibecodeschool.com/learn/aa-01-how-llms-actually-work)
- [Course 01 · What Is Claude Code](https://vibecodeschool.com/learn/cc-01-what-is-claude-code)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/ai) · added 2026-09-12
