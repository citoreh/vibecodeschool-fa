<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# MCP

> Model Context Protocol: an open standard for plugging external tool servers into any agent harness.

*§03 Tools & Environment · also called: Model Context Protocol, MCP server, Connector · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/mcp)*

MCP, the Model Context Protocol, is an open standard for connecting a [harness](./harness.md) to outside capabilities. An MCP server is a small program that advertises [tools](./tool.md) (and sometimes resources and prompt templates) over a simple JSON interface; the harness lists those tools next to its built-in ones, and the [model](./model.md) calls them the same way. One server for GitHub, one for Postgres, one for your browser, and any MCP-aware client can use all three without custom glue.

The pitch is portability: write the integration once, use it from Claude Code, Cursor, Codex, Claude Cowork and the rest. The catch is [context](./context.md). Every connected server adds its tool definitions to every request, and popular servers ship dozens of tools. Five servers can quietly eat a large slice of your [context window](./context-window.md) before you type a word, and a crowded tool list makes the agent worse at choosing. A slow or flaky server also stalls the whole loop while the [tool call](./tool-call.md) waits.

Connect servers per project, not globally, and only the ones the current work needs. Prefer servers with a few well-described tools over kitchen-sink ones. For anything that touches production data, check what permissions the server holds; from the model's point of view an MCP tool is just another action it is allowed to take, and [prompt injection](./prompt-injection.md) through a server's results is a real path.

## In the tools

- Claude Code: `claude mcp add` registers a server for a project or for you globally; its tools appear with an `mcp__` prefix.
- Claude Cowork and claude.ai: connectors are MCP servers behind a friendlier name; Gmail, Calendar and Drive are examples.
- Cursor and Codex: servers are declared in a config file in the workspace and toggled in settings.

## In conversation

> “I want it to file Linear tickets from the failing tests.”
>
> “Add the Linear MCP server to the project config. It shows up as a tool, and the agent can create issues directly instead of you pasting.”
>
> “Just that one server, right? Last time a toolbar's worth of servers made it sluggish.”

**Related:** [Environment](./environment.md) · [Permission request](./permission-request.md) · [Skill](./skill.md) · [Tool result](./tool-result.md)

## Learn it in the school

- [Course 01 · MCP Servers](https://vibecodeschool.com/learn/cc-17-mcp-servers)
- [Course 04 · MCP — Model Context Protocol](https://vibecodeschool.com/learn/aa-12-mcp-model-context-protocol)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/mcp) · added 2026-09-12
