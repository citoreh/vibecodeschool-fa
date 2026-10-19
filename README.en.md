<div align="center">

# Vibe Code School

### Learn vibe coding free — the roadmap, 7 interactive courses, an AI coding dictionary and an awesome list, open source.

**170 lessons · 7 courses · 81-term dictionary · 158 "can I vibe code it?" verdicts · 14 AI career roadmaps**

[**Start learning free →**](https://vibecodeschool.com) · [Roadmap](https://vibecodeschool.com/roadmap) · [AI Coding Dictionary](./dictionary/README.md) · [Claude Code Cheat Sheet](https://vibecodeschool.com/claude-code-cheat-sheet) · [Awesome list](./awesome/README.md)

[![Website](https://img.shields.io/badge/vibecodeschool.com-live-3553ff)](https://vibecodeschool.com)
[![License: MIT](https://img.shields.io/badge/code-MIT-green.svg)](./LICENSE)
[![License: CC BY-SA 4.0](https://img.shields.io/badge/content-CC%20BY--SA%204.0-lightgrey.svg)](./LICENSE-CONTENT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](./CONTRIBUTING.md)

</div>

---

## What is vibe coding?

**Vibe coding** is building software at the level of intent: you describe outcomes, an
AI coding agent — [Claude Code](https://vibecodeschool.com/courses/claude-code-vibe-coding),
[OpenAI Codex](https://vibecodeschool.com/courses/codex-mobile-apps), Cursor,
[Google Antigravity](https://vibecodeschool.com/courses/antigravity-agent-manager) —
edits the files, runs the tests and executes the commands, and you review, correct and
steer. It is the fastest-growing way to build software in 2026, and most of what teaches
it is a YouTube tour, not a curriculum.

This repo is the open-source home of [Vibe Code School](https://vibecodeschool.com): the
full **vibe coding roadmap**, the outline of **all 170 lessons**, the **AI Coding
Dictionary** as plain markdown, working **demo apps with their build logs**, copy-paste
**templates** (CLAUDE.md, AGENTS.md, slash commands, hooks), and a curated **awesome list**.
The interactive versions — agent-session replays you scrub through, hands-on steps,
quizzes, XP and streaks — are free on the site, no signup required.

## 🗺️ The roadmap

**[→ roadmap/README.md](./roadmap/README.md)** — the full learning path from "never
opened a terminal" to running a fleet of agents, with a diagram, a module-by-module
breakdown and an FAQ. Interactive version with progress tracking:
[vibecodeschool.com/roadmap](https://vibecodeschool.com/roadmap).

## 📚 The courses

| # | Course | Level | Lessons | Outline | Take it |
|---|--------|-------|---------|---------|---------|
| 01 | **Vibe Coding using Claude Code** | Beginner | 28 | [outline](./courses/claude-code-vibe-coding/README.md) | [start free →](https://vibecodeschool.com/courses/claude-code-vibe-coding) |
| 02 | **Build Mobile Apps using Codex** | Intermediate | 25 | [outline](./courses/codex-mobile-apps/README.md) | [start free →](https://vibecodeschool.com/courses/codex-mobile-apps) |
| 03 | **Agent Manager with Google Antigravity** | Advanced | 25 | [outline](./courses/antigravity-agent-manager/README.md) | [start free →](https://vibecodeschool.com/courses/antigravity-agent-manager) |
| 04 | **Agentic AI Engineering** — RAG, MCP, evals, AI security | Intermediate | 25 | [outline](./courses/agentic-ai/README.md) | [start free →](https://vibecodeschool.com/courses/agentic-ai) |
| 05 | **Prompt Engineering Mastery** | Beginner | 35 | [outline](./courses/prompt-engineering/README.md) | [start free →](https://vibecodeschool.com/courses/prompt-engineering) |
| 06 | **Claude Cowork: AI for Everyday Work** | Beginner | 16 | [outline](./courses/claude-cowork/README.md) | [start free →](https://vibecodeschool.com/courses/claude-cowork) |
| 07 | **ChatGPT Work: Delegate the Busywork** | Beginner | 16 | [outline](./courses/chatgpt-work/README.md) | [start free →](https://vibecodeschool.com/courses/chatgpt-work) |

Every lesson is a walkthrough you run on your own machine, a sandbox replay you scrub
through turn by turn, or a concept lesson — gated by a quiz before you can mark it
complete. Finish a course, print a
[free certificate](https://vibecodeschool.com/certificate). Builders start with Course 01;
non-coders start with Claude Cowork or ChatGPT Work.

## 📖 The AI Coding Dictionary

**[→ dictionary/README.md](./dictionary/README.md)** — 81 agentic-coding terms in plain
English, one markdown file each: context window, compaction, harness, hooks, subagents,
skills, AGENTS.md / CLAUDE.md, permission modes, plan mode, worktrees, headless mode,
prompt injection, AFK, human-in-the-loop, vibe coding itself. Each entry covers the
mechanism, the symptom you'll recognise, what to do about it, and how the concept shows
up in Claude Code, Codex and Cursor. **Updated weekly** by a scheduled agent.
Interactive version with search and cross-links:
[vibecodeschool.com/ai-coding-dictionary](https://vibecodeschool.com/ai-coding-dictionary).

Companion reference on the site: the
**[Claude Code Cheat Sheet](https://vibecodeschool.com/claude-code-cheat-sheet)** — every
command, slash command, permission mode, config file, hook event and MCP command on one page.

## 🧪 Live demos — apps + every prompt that built them

**[→ demos/](./demos/README.md)** — small apps vibe-coded with Claude Code,
[running live on the site](https://vibecodeschool.com/demos). Each folder has the
**full prompt-by-prompt build log** (including the bugs and how the corrections were
phrased), the **exact source** (MIT), and a **remix prompt** to rebuild it yourself:

| Demo | The teaching point | |
|------|--------------------|---|
| [Tip Splitter](./demos/tip-splitter/) | Small turns + honest edge cases (the cent-rounding overpay) | [live ▶](https://vibecodeschool.com/demos/tip-splitter) |
| [Focus Timer](./demos/focus-timer/) | A real React StrictMode interval bug, diagnosed and fixed properly | [live ▶](https://vibecodeschool.com/demos/focus-timer) |
| [CLAUDE.md Generator](./demos/claude-md-generator/) | Templates beat blank pages — project memory as a form | [live ▶](https://vibecodeschool.com/demos/claude-md-generator) |

## 🧰 Templates — copy-paste the toolchain

**[→ templates/](./templates/README.md)** — the artifacts the courses teach you to build,
ready to adapt:

- **[CLAUDE.md templates](./templates/claude-md/)** — project memory for web apps, Expo
  mobile apps and monorepos (or [generate one from a form](https://vibecodeschool.com/demos/claude-md-generator))
- **[Slash commands](./templates/slash-commands/)** — `/review-pr`, `/add-tests`,
  `/fix-issue`, `/draft-changelog`, `/find-todos`, `/explain`
- **[Hook recipes](./templates/hooks/)** — auto-format on edit, protect files, test after change
- **[AGENTS.md template](./templates/agents-md/)** — the cross-tool / Codex counterpart

## 😎 Awesome Vibe Coding

**[→ awesome/README.md](./awesome/README.md)** — a curated list of vibe coding tools
(Claude Code, Codex, Cursor, Antigravity, Gemini CLI, Aider…), courses across every
platform (including our competitors — it's an honest list), tutorials, communities and
reference reading.

## More on the site

- **[Can I Vibe Code It?](https://vibecodeschool.com/can-i-vibe-code-it)** — 158 popular
  SaaS tools with an honest verdict on whether you can vibe-code a personal alternative,
  plus the one-shot prompt to build it.
- **[AI career roadmaps](https://vibecodeschool.com/careers)** — 14 AI-era roles
  (Forward Deployed Engineer, Vibe Coder, Agent Engineer, AI PM…) with skills, salaries
  and proof-of-work checkpoints.
- **[Agents compared](https://vibecodeschool.com/compare)** — Claude Code vs Codex,
  Claude Code vs Cursor, Claude Cowork vs ChatGPT Work, and more.
- **[How to vibe code anything](https://vibecodeschool.com/how-to-vibe-code)** — a game,
  a mobile app, a Chrome extension, a SaaS, a Discord bot, a dashboard, a portfolio.
- **[Field notes](https://vibecodeschool.com/blog)** — the best vibe coding courses
  compared, learning from scratch, bootcamps, platforms.
- For AI assistants: [llms.txt](https://vibecodeschool.com/llms.txt) and
  [llms-full.txt](https://vibecodeschool.com/llms-full.txt).

## 🤝 Contributing

Spotted an outdated fact in a lesson or a dictionary entry? Know a tool the awesome list
is missing? Want to translate the roadmap? **PRs are welcome** — see
[CONTRIBUTING.md](./CONTRIBUTING.md). Curriculum and dictionary files are generated from
the site's source of truth, so content fixes get applied there and re-exported with
credit to you.

## ⭐ Star history

If this roadmap, the courses or the dictionary help you, **star the repo** — stars are
how other learners find it.

[![Star History Chart](https://api.star-history.com/svg?repos=dineshxr/vibecodeschool&type=Date)](https://star-history.com/#dineshxr/vibecodeschool&Date)

## 📜 License & credits

- **Code** (scripts, site snippets, demo sources): [MIT](./LICENSE)
- **Content** (roadmap, course outlines, lesson text, dictionary): [CC BY-SA 4.0](./LICENSE-CONTENT) — reuse freely with attribution and keep derivatives open.

Built by **[Dinesh Puppala](https://github.com/dineshxr)** ([vibecodeschool.com](https://vibecodeschool.com)).

<div align="center">

**[Start the first lesson free →](https://vibecodeschool.com)**

</div>
