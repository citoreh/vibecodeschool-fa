<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Model provider

> The service that actually runs the model: a lab like Anthropic or OpenAI, a cloud reselling it, or your own laptop through Ollama.

*§01 The Model · also called: Provider, Inference provider · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/model-provider)*

A model provider is the service that runs [inference](./inference.md) for you. Usually that's the lab that trained the [model](./model.md) (Anthropic, OpenAI, Google), sometimes a cloud that resells it (Amazon Bedrock, Google Vertex, Microsoft Azure), and sometimes your own hardware running an open-weight model through Ollama or llama.cpp. The [harness](./harness.md) sends each [model provider request](./model-provider-request.md) to the provider and gets tokens back.

The distinction matters because the provider, not the harness, sets the limits you bump into: price per [token](./token.md), rate limits, the [context window](./context-window.md) size, which features exist (prompt caching, extended thinking, batch discounts) and how long the [prefix cache](./prefix-cache.md) lives. When the same tool behaves differently on two accounts, check whether they're pointed at different providers or tiers.

Most coding harnesses let you swap the provider. Claude Code can route to Bedrock or Vertex for teams that already pay a cloud. Codex and Cursor can be pointed at other endpoints or your own keys. Local providers give you privacy and no per-token bill, at the cost of weaker models. Pick on capability first; a cheap provider that can't finish the task isn't cheap.

## In the tools

- Claude Code: environment variables switch the provider to Amazon Bedrock or Google Vertex AI without changing the workflow.
- Codex: `model_provider` in the config file points the CLI at a different OpenAI-compatible endpoint.
- Cursor: the model list mixes several providers; you can add your own API keys in settings.

## In conversation

> “Our security team won't allow direct calls to Anthropic.”
>
> “Route Claude Code through Bedrock then. Same model, different provider, and it stays inside your AWS account.”

**Related:** [Usage limit](./usage-limit.md) · [Input tokens](./input-tokens.md) · [Output tokens](./output-tokens.md)

## Learn it in the school

- [Course 04 · The Modern AI Stack](https://vibecodeschool.com/learn/aa-04-the-modern-ai-stack)
- [Course 04 · Running Models Locally with Ollama](https://vibecodeschool.com/learn/aa-17-local-models-ollama)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/model-provider) · added 2026-09-12
