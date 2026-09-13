<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Tool call

> The model's request to run a tool: a structured message naming the tool and its arguments, which the harness then executes.

*§03 Tools & Environment · also called: Function call, Tool use · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/tool-call)*

A tool call is what the [model](./model.md) produces when it decides to use a [tool](./tool.md): a small structured message that names the tool and fills in its arguments, for example `Read` with a file path or `Bash` with a command string. It is still just generated text. The [harness](./harness.md) parses it, checks it against the current [permission mode](./permission-mode.md), runs the real function, and feeds the [tool result](./tool-result.md) back into the [context window](./context-window.md) for the next request.

Each tool call is a round trip. The model can't run a command and keep thinking in the same breath; it has to emit the call, wait for the harness, and then be invoked again with the result attached. That is why a [turn](./turn.md) with thirty tool calls means thirty-plus [provider requests](./model-provider-request.md), why long investigations feel slow, and why the bill climbs even when the agent 'only read some files'. Every call also adds its result to the context, so a noisy command with pages of output costs twice: once in latency and once in attention.

You can read tool calls like a log. When an agent goes wrong, the trail of calls usually shows exactly where: the file it never opened, the test it ran before making the change, the search that returned nothing and was ignored. Reviewing that trail is faster than re-reading the prose the agent wrote about it.

## In the tools

- Claude Code: each call shows in the transcript as a collapsible line with the tool name and arguments, so you can audit what it did.
- Codex: the app renders calls as command previews and asks for approval on anything outside the sandbox.
- Antigravity: tool calls are recorded in the task's audit trail alongside screenshots and recordings.

## In conversation

> “Why is a two-line fix taking four minutes?”
>
> “Look at the tool calls. It grepped, read six files, ran the test suite twice and then edited. Each one is a full round trip to the model.”
>
> “Fine, but I'd rather it read six files than guess.”

**Related:** [Hooks](./hooks.md) · [Inference](./inference.md) · [Automated check](./automated-check.md)

## Learn it in the school

- [Course 01 · The Agentic Loop](https://vibecodeschool.com/learn/cc-04-the-agentic-loop)
- [Course 03 · Reading the Audit Trail](https://vibecodeschool.com/learn/ag-17-observability)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/tool-call) · added 2026-09-12
