<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Slash command

> A typed /name shortcut that runs a built-in action or expands a saved prompt, so the prompts you reuse live in the repo.

*§03 Tools & Environment · also called: Custom command, Prompt shortcut, /command · [interactive version](https://vibecodeschool.com/ai-coding-dictionary/slash-command)*

A slash command is a shortcut you type into the [agent](./agent.md)'s input, `/name`, that either triggers a built-in action or expands into a stored prompt. Built-ins handle the [harness](./harness.md) itself: `/clear` to start a fresh [session](./session.md), `/compact` to trigger [compaction](./compaction.md), `/init` to draft an [AGENTS.md](./agents-md.md), `/help`. Custom commands are prompt files you keep in the project; typing `/review` might paste a two-paragraph review checklist with the current diff attached, and the [model](./model.md) takes it from there.

Custom commands solve the 'I keep typing the same thing' problem, and they solve it better than putting the text in a rules file. Anything in the rules file is loaded into every turn whether relevant or not, spending [context](./context.md) on instructions the current task doesn't need. A slash command loads its text only when you call it. That makes it the right home for long, occasional prompts: the release checklist, the migration playbook, the 'write a field note about this' template.

Keep commands in the repo so the whole team gets them, give them arguments where it helps (`/fix-issue 123`), and let them reference files rather than inline everything. When a command needs supporting scripts or several steps, it has outgrown the format and should become a [skill](./skill.md). A good test: if a new teammate would benefit from the shortcut on day one, commit it.

## In the tools

- Claude Code: custom commands are markdown files in `.claude/commands/` (project) or `~/.claude/commands/` (personal); `$ARGUMENTS` passes whatever you typed after the name.
- Most tools: saved prompts exist under other names (rules, notepads, prompt files); the idea is the same, load a reusable prompt on demand.

## In conversation

> “How are you getting such consistent PR descriptions out of it?”
>
> “A slash command. /pr expands to our template plus the diff summary, so every description follows the same shape.”
>
> “Send me the file, I'll drop it into our commands folder.”

**Related:** [Progressive disclosure](./progressive-disclosure.md) · [Hooks](./hooks.md) · [Context pointer](./context-pointer.md)

## Learn it in the school

- [Course 01 · Slash Commands](https://vibecodeschool.com/learn/cc-12-slash-commands)
- [Course 01 · Writing Your Own Slash Command](https://vibecodeschool.com/learn/cc-13-custom-slash-commands)

---

Part of the [AI Coding Dictionary](./README.md) by [Vibe Code School](https://vibecodeschool.com) · [read this entry on the site](https://vibecodeschool.com/ai-coding-dictionary/slash-command) · added 2026-09-12
