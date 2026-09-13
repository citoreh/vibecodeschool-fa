<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Skill

> A named, reusable procedure the agent loads on demand: a folder of instructions and optional scripts, used when a task matches.

*§06 Memory & Steering · also called: Agent skill, SKILL.md, Skills · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/skill)*

A skill is a packaged procedure an [agent](./agent.md) can pick up when a task calls for it. In practice it is a folder with a `SKILL.md` describing what the skill does and when to use it, followed by the step-by-step instructions, and sometimes scripts or templates alongside. The [harness](./harness.md) shows the agent only the name and description until the skill is invoked, then loads the body into [context](./context.md). That makes skills a working example of [progressive disclosure](./progressive-disclosure.md).

Skills exist because repeated instructions rot in chat. A deploy procedure you explain in a prompt is gone when the [session](./session.md) ends, and the version you paste next week drifts from the version you pasted last week. Putting it in a skill gives it a home, a name, and a single place to fix. The failure mode is the same as with [AGENTS.md](./agents-md.md): skills that try to do too much, or ten near-duplicate skills whose descriptions blur together so the agent picks the wrong one.

Write a skill for anything you have explained twice. Keep the description specific enough that the agent can tell when it applies. Put deterministic steps in scripts the skill can run, and keep the prose for judgment calls. Skills differ from a [slash command](./slash-command.md), which you trigger by hand, in that the agent can choose to use a skill itself, and from a [subagent](./subagent.md) in that a skill runs inside the current session's context rather than in a separate one.

## In the tools

- Claude Code: skills live in `.claude/skills/<name>/SKILL.md` (project) or `~/.claude/skills/` (personal), invoked by name or chosen by the agent.
- Claude Cowork: skills teach it your way of doing a job, such as how your team formats a weekly report.
- Codex: recent versions read the same `SKILL.md` convention from a skills directory; check your version's docs for the path.

## In conversation

> “Every release I re-explain the changelog format and it still gets it slightly wrong.”
>
> “Make it a skill. Description: 'writing release notes'. Body: the format, the sections, one example.”
>
> “Do I have to invoke it?”
>
> “You can with a slash, but it'll also pick it up on its own when you say 'draft the release notes'.”

**Related:** [MCP](./mcp.md) · [Hooks](./hooks.md) · [Context engineering](./context-engineering.md)

## Learn it in the school

- [Course 01 · Agent Skills](https://vibecodeschool.com/learn/cc-28-agent-skills)
- [Course 06 · Skills: Teach It Your Way of Working](https://vibecodeschool.com/learn/cw-11-skills-teach-it-your-way)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/skill) · added 2026-09-12
