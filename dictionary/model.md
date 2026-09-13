<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Model

> The trained network itself: billions of parameters that turn a context into the next token, and nothing more.

*§01 The Model · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/model)*

A model is the trained neural network: a very large set of [parameters](./parameters.md) that, given a sequence of [tokens](./token.md), produces a probability for what the next token should be. That's the entire job. It doesn't read your repo, doesn't remember yesterday, doesn't run tests. Every one of those abilities is added by the [harness](./harness.md) around it.

This is why the same model behaves so differently in different products. Claude Sonnet in a chat window answers questions; the same model inside Claude Code edits files and runs your test suite. The model didn't change; what changed is the [system prompt](./system-prompt.md), the [tools](./tool.md) on offer and the loop that feeds results back in. When behaviour shifts between two products, suspect the wrapper before the weights.

The model is also [stateless](./stateless.md): it holds nothing between calls. Each request starts from a blank slate and sees only what the harness sends. When you pick a model in a dropdown (Sonnet vs Opus, GPT-5 vs a mini variant) you're trading capability against speed and price, but you are never changing what it can perceive. That's the harness's job.

## In the tools

- Claude Code: `/model` switches between Claude models mid-session; everything else about the session stays the same.
- Codex: the model is set in config or the model picker; the CLI is the harness that gives it a sandbox and tools.
- Ollama: runs open-weight models locally; the same model file behaves differently depending on which harness calls it.

## In conversation

> “Should I switch models? It keeps missing the config file.”
>
> “It can't see the config file. Same model, different context, and it'd be fine. Point it at the path first.”

**Related:** [Model provider](./model-provider.md) · [Inference](./inference.md) · [Next-token prediction](./next-token-prediction.md)

## Learn it in the school

- [Course 04 · How LLMs Actually Work](https://vibecodeschool.com/learn/aa-01-how-llms-actually-work)
- [Course 02 · Codex vs Claude Code](https://vibecodeschool.com/learn/cm-03-codex-vs-claude-code)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/model) · added 2026-09-12
