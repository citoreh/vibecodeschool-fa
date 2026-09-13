<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Model provider request

> A single API call: the harness ships the full context to the provider and gets one reply back. Most turns need several of them.

*§01 The Model · also called: API call, Model call, Request · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/model-provider-request)*

A model provider request is a single round trip to the [model provider](./model-provider.md): the [harness](./harness.md) ships the entire [context window](./context-window.md) (system prompt, conversation, tool definitions, every tool result so far) and gets back one response, which is either a message for you or a [tool call](./tool-call.md). Because the model is [stateless](./stateless.md), nothing is kept on the provider side between requests; the full context is re-sent every time.

A single [turn](./turn.md) usually contains many of these. You ask for a fix; the harness makes one request; the model asks to read a file; the harness reads it and makes a second request with the file contents appended; the model asks to run tests; a third request. A turn with fifteen tool calls is sixteen requests, and each one re-reads everything that came before. That's why cost per turn climbs as a session grows, and why the [prefix cache](./prefix-cache.md) matters so much.

You'll rarely see requests directly, but you feel them: each is a pause while the model reads and thinks, and each is a line on the bill. Fewer, more useful tool calls beat many small ones. A well-targeted search that returns the right file in one go is cheaper than five reads that hunt for it.

## In the tools

- Claude Code: `/cost` totals the requests made this session; the spinner with a changing verb is one request in flight.
- Anthropic API: one `messages` call is one request; tool use means you loop, sending results back in a new call.

## In conversation

> “It only did three edits but the cost jumped by a dollar.”
>
> “Count the requests, not the edits. Every tool call is another full round trip with the whole session attached.”

**Related:** [Inference](./inference.md) · [Input tokens](./input-tokens.md) · [Cache tokens](./cache-tokens.md)

## Learn it in the school

- [Course 01 · The Agentic Loop](https://vibecodeschool.com/learn/cc-04-the-agentic-loop)
- [Course 04 · Function Calling & Structured Outputs](https://vibecodeschool.com/learn/aa-03-function-calling-structured-outputs)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/model-provider-request) · added 2026-09-12
