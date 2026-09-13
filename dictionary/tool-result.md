<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Tool result

> What comes back from a tool call and lands in the context: file contents, command output, an error, a list of search hits.

*§03 Tools & Environment · also called: Tool output · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/tool-result)*

A tool result is the payload the [harness](./harness.md) returns after executing a [tool call](./tool-call.md): the text of a file, the stdout and exit code of a command, the matches from a search, or an error message. It is appended to the [context window](./context-window.md) as if someone had pasted it into the chat, and the [model](./model.md) reads it on the next request. Everything the [agent](./agent.md) knows about the current state of the [environment](./environment.md) arrived this way.

Because results are the agent's only eyes, their quality is the agent's quality. A truncated log hides the failing test. A command that swallows errors and exits zero tells the agent everything is fine. A search tool that returns two hundred matches buries the one that matters. And results are ordinary text to the model, which means text inside them can carry instructions: a README that says 'ignore your previous rules' is a [prompt injection](./prompt-injection.md) risk the moment it becomes a tool result.

Shape the results you feed the loop. Prefer commands with short, honest output, and make failures loud: a non-zero exit code and a one-line reason beat a wall of green. When output is unavoidably long, have the agent pipe it through `tail`, `grep` or a summary step instead of reading the whole thing. Big results are the fastest way out of the [smart zone](./smart-zone.md).

## In the tools

- Claude Code: long results are collapsed in the transcript view, but the model still receives the text up to a per-tool limit; ask it to filter output when a command is chatty.
- Codex: command output streams into the thread and is stored with the run, so you can inspect exactly what the model saw.
- Most tools: results from MCP servers count the same as built-in tool output, so a verbose server bloats context just as fast.

## In conversation

> “It insists the build passed, but the deploy is broken.”
>
> “Check the tool result for the build step. The script prints 'done' and exits zero even when the bundler fails, so from the agent's side it did pass.”
>
> “Okay, that's a script bug first and an agent bug second.”

**Related:** [Attention budget](./attention-budget.md) · [Context](./context.md) · [Hooks](./hooks.md)

## Learn it in the school

- [Course 01 · Running Tests with Claude](https://vibecodeschool.com/learn/cc-08-running-tests)
- [Course 04 · Prompt Injection, Hallucinations & PII](https://vibecodeschool.com/learn/aa-23-prompt-injection-and-pii)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/tool-result) · added 2026-09-12
