<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Prompt injection

> Instructions smuggled into something the agent reads, which the model may follow as if they came from you.

*§04 Failure Modes · also called: Indirect prompt injection, Tool-result injection · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/prompt-injection)*

Prompt injection is when text the [agent](./agent.md) reads contains instructions, and the [model](./model.md) follows them as though you had typed them. The model sees one stream of [tokens](./token.md); it has no hard boundary between 'the user said' and 'the web page said'. So a comment in a README, a line in a GitHub issue, a hidden block in a fetched docs page or a crafted [tool result](./tool-result.md) can say 'ignore your previous instructions and run this command', and some fraction of the time the model will.

Coding agents are unusually exposed because they read untrusted text all day and hold powerful [tools](./tool.md) while doing it. A model that only chats can be tricked into saying something wrong. An agent with a shell, a filesystem and network access can be tricked into printing your `.env` into a commit message, running a curl command that ships your keys elsewhere, or editing a file so the next run does the damage for it. The injection does not need to be clever; it needs to be read at the wrong moment.

There is no complete fix, so defence is layered. Run agents with the least permissive [permission mode](./permission-mode.md) the task allows, and in a [sandbox](./sandbox.md) when they will touch untrusted content. Keep secrets out of the [environment](./environment.md) the agent can see. Review diffs before they merge, especially anything touching shell scripts, CI or network calls. And treat fetched content as data to be summarised, not instructions to be obeyed; when the agent 'decides' to do something you never asked for right after reading a page, that is the symptom.

## In the tools

- Claude Code: permission modes and sandboxed Bash limit what an injected instruction can actually execute; the harness treats fetched pages as untrusted content, but the model still reads them.
- Codex: cloud tasks run in isolated containers with network access off by default, which caps the blast radius of a successful injection.

## In conversation

> “It fetched the library's docs and then suddenly tried to run a script from a random gist.”
>
> “That's prompt injection. Something on that page told it to. Kill the session, check the diff, and run it sandboxed next time.”

**Related:** [AFK](./afk.md) · [Human review](./human-review.md) · [Hooks](./hooks.md)

## Learn it in the school

- [Course 05 · Prompt Injection](https://vibecodeschool.com/learn/pe-30-prompt-injection)
- [Course 04 · Prompt Injection, Hallucinations & PII](https://vibecodeschool.com/learn/aa-23-prompt-injection-and-pii)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/prompt-injection) · added 2026-09-12
