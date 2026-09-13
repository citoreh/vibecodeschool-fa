<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# The AI Coding Dictionary

**81 agentic-coding terms in plain English** — the vocabulary of vibe coding with
Claude Code, OpenAI Codex, Cursor and Google Antigravity: context windows, compaction,
harnesses, hooks, subagents, AGENTS.md and CLAUDE.md, permission modes, prompt injection
and more. Each entry gives the one-line definition, the mechanism, the symptom you'll
recognise, what to do about it, how it shows up in each tool, and a usage dialogue.

Interactive version with search, cross-links and course links:
**[vibecodeschool.com/ai-coding-dictionary](https://vibecodeschool.com/ai-coding-dictionary)**

Updated weekly — last update **2026-09-12**. A scheduled agent checks the term list
against [mattpocock/dictionary-of-ai-coding](https://github.com/mattpocock/dictionary-of-ai-coding)
and the tools' changelogs every Monday; every definition here is written from scratch
(content licence: CC BY-SA 4.0).

## §01 The Model

*What a model is, what it isn't, and where the bill comes from.*

- **[AI](./ai.md)** — An umbrella word that keeps changing what it points at. In coding today it means a language model plus the harness that lets it act.
- **[Model](./model.md)** — The trained network itself: billions of parameters that turn a context into the next token, and nothing more.
- **[Parameters](./parameters.md)** — The billions of numbers a model is made of, fixed once training ends. Also called weights. What the model knows by heart lives in them.
- **[Training](./training.md)** — How a model's weights get their values: predicting text at huge scale, then rounds of feedback that shape it into an assistant.
- **[Inference](./inference.md)** — Using the model rather than training it. Every reply, edit and tool call you see comes from an inference pass; the weights never move.
- **[Effort](./effort.md)** — How hard the model thinks before replying. Turn it up for tricky problems and pay in tokens and wait; turn it down for routine edits.
- **[Token](./token.md)** — The unit a model reads and writes in — a word fragment, a little shorter than a word — and the unit every limit and price uses.
- **[Next-token prediction](./next-token-prediction.md)** — The model's one trick: pick a likely next token, stick it on the end, go again. Prose, code and tool calls all come out this way.
- **[Non-determinism](./non-determinism.md)** — Run the same prompt twice and you can get two different answers. Sampling, batching and silent provider updates all contribute.
- **[Model provider](./model-provider.md)** — The service that actually runs the model: a lab like Anthropic or OpenAI, a cloud reselling it, or your own laptop through Ollama.
- **[Harness](./harness.md)** — The software around the model that gives it hands: a system prompt, tools, permissions, hooks and the loop that feeds results back.
- **[Model provider request](./model-provider-request.md)** — A single API call: the harness ships the full context to the provider and gets one reply back. Most turns need several of them.
- **[Input tokens](./input-tokens.md)** — Everything the model reads on a request: instructions, history, tool definitions, results. Cheap per token, but there are a lot of them.
- **[Output tokens](./output-tokens.md)** — What the model writes: replies, code, tool calls, hidden thinking. Produced one by one, so they set the wait, and they cost the most.
- **[Prefix cache](./prefix-cache.md)** — The provider remembers the start of your last prompt, so the next request that begins the same way is faster and much cheaper.
- **[Cache tokens](./cache-tokens.md)** — The share of a request's input served from the prefix cache. Heavily discounted, and the first thing to check when a session feels pricey.
- **[Usage limit](./usage-limit.md)** — The cap on how much agent work your plan or API key allows in a window. Hitting it pauses you; it isn't the context window.

## §02 Sessions, Context Windows & Turns

*The unit of work: what the agent sees, how long it lasts, and why it forgets.*

- **[Stateless](./stateless.md)** — Nothing carries over on its own: each model request starts from zero, and each new session does too.
- **[Context](./context.md)** — Everything the agent currently has in front of it that bears on the task: loaded files, your messages, tool results so far.
- **[Context window](./context-window.md)** — The fixed-size buffer of tokens a model can read in one request; if something isn't in it, the model can't see it.
- **[Stateful](./stateful.md)** — Carries information forward from one step to the next; a session is stateful across turns even though the model underneath is not.
- **[Agent](./agent.md)** — A model wired to tools and a loop: it reads, acts, checks the result, and goes again until the task is done or you stop it.
- **[System prompt](./system-prompt.md)** — The standing instructions the harness puts in front of every request: who the agent is, what tools it has, how it should behave.
- **[Session](./session.md)** — One continuous run with an agent, from an empty context to the moment you clear it, close it, or hand its work off.
- **[Turn](./turn.md)** — Your message and all the work the agent does before it hands control back to you.
- **[Steering](./steering.md)** — Nudging a running agent back on course, mid-turn or between turns, before a wrong call becomes the foundation for everything after it.

## §03 Tools & Environment

*How an agent touches the world: files, shells, permissions, and sandboxes.*

- **[Environment](./environment.md)** — Everything outside the harness the agent can inspect or change: your repo, your shell, the services it can reach, the browser it drives.
- **[Filesystem](./filesystem.md)** — The directory tree the agent reads, edits and runs inside; for a coding agent, the main part of the environment.
- **[Tool](./tool.md)** — A named capability the harness lets the model invoke, such as reading a file, running a shell command or fetching a page.
- **[Tool call](./tool-call.md)** — The model's request to run a tool: a structured message naming the tool and its arguments, which the harness then executes.
- **[Tool result](./tool-result.md)** — What comes back from a tool call and lands in the context: file contents, command output, an error, a list of search hits.
- **[MCP](./mcp.md)** — Model Context Protocol: an open standard for plugging external tool servers into any agent harness.
- **[Permission request](./permission-request.md)** — The harness pausing before a risky tool call to ask you yes or no; the simplest human-in-the-loop gate there is.
- **[Permission mode](./permission-mode.md)** — The setting that decides which tool calls run automatically and which stop for a permission request.
- **[Agent mode](./agent-mode.md)** — A named preset that bundles a permission mode with behavioural instructions, switchable in the middle of a session.
- **[Plan mode](./plan-mode.md)** — A read-only agent mode: the agent may search and read, but must propose a plan for your approval before it edits anything.
- **[Sandbox](./sandbox.md)** — An isolated place for the agent to run, such as a container, VM or restricted shell, so a bad action can't reach the rest of your machine.
- **[Hooks](./hooks.md)** — Commands you configure the harness to run at fixed moments, such as before or after a tool call, regardless of what the model wants.
- **[Slash command](./slash-command.md)** — A typed /name shortcut that runs a built-in action or expands a saved prompt, so the prompts you reuse live in the repo.
- **[Worktree](./worktree.md)** — A second checkout of the same git repo in its own directory, so an agent can work on a branch without touching yours.
- **[Headless mode](./headless-mode.md)** — Running the agent from a script or CI with a prompt and no interactive UI; the result comes back as text or JSON.
- **[Checkpoint](./checkpoint.md)** — A saved state of your files, and sometimes the conversation, that you can rewind to after a turn goes wrong.

## §04 Failure Modes

*The ways it goes wrong: confident nonsense, stale knowledge, and long-session drift.*

- **[Sycophancy](./sycophancy.md)** — The model's tilt toward agreeing with you, praising your plan, and telling you it worked, regardless of whether it did.
- **[Hallucination](./hallucination.md)** — Output that is fluent, confident, and wrong: an invented API, a misquoted file, a test result that never happened.
- **[Parametric knowledge](./parametric-knowledge.md)** — What the model knows because it was in the training data, stored in its weights and frozen from that moment on.
- **[Knowledge cutoff](./knowledge-cutoff.md)** — The date the model's training data ends; anything released after it is unknown to the model unless you load it into context.
- **[Contextual knowledge](./contextual-knowledge.md)** — Facts the model has because they are in the context window right now, as opposed to facts it remembers from training.
- **[Attention relationship](./attention-relationship.md)** — The link between any two tokens in the context; the model weighs each pair, and there are far more pairs than tokens.
- **[Attention budget](./attention-budget.md)** — The fixed amount of focus each token can spread across the rest of the context; more context means thinner slices.
- **[Attention degradation](./attention-degradation.md)** — The slow drop in output quality as a session grows and every token's attention is spread across more competing material.
- **[Smart zone](./smart-zone.md)** — The early stretch of a session where the agent is at its sharpest; past it, the same model gets sloppier and forgetful.
- **[Prompt injection](./prompt-injection.md)** — Instructions smuggled into something the agent reads, which the model may follow as if they came from you.

## §05 Handoffs

*Moving work between sessions without losing the plot.*

- **[Clearing](./clearing.md)** — Wiping the session so the next request starts from an empty context window, keeping only the standing instructions.
- **[Handoff](./handoff.md)** — Ending one session and starting another on the same task, carrying the state forward in writing rather than in the window.
- **[Primary source](./primary-source.md)** — The real thing: the file, the diff, the test output, the docs page. What the agent should read instead of a description of it.
- **[Secondary source](./secondary-source.md)** — An account of the thing rather than the thing itself: a summary, a paraphrase, a compaction. Useful, but one step removed from the truth.
- **[Handoff artifact](./handoff-artifact.md)** — The written note that carries a task across a session boundary: what's done, what's left, what was decided, where to look.
- **[Spec](./spec.md)** — A written description of what to build and how you'll know it's right, agreed before the agent starts writing code.
- **[Ticket](./ticket.md)** — A bounded unit of work with a clear done state, sized so an agent can finish it in one session.
- **[Compaction](./compaction.md)** — Replacing the session so far with a shorter summary of it, freeing the context window at the cost of detail.
- **[Autocompact](./autocompact.md)** — Compaction the harness triggers on its own when the context window nears its limit, without asking you first.

## §06 Memory & Steering

*Getting instructions to stick across sessions, and pointing the agent at the right thing.*

- **[Memory system](./memory-system.md)** — Whatever lets an agent carry information across sessions: notes on disk, a memory directory, a store it reads at startup.
- **[AGENTS.md](./agents-md.md)** — The instructions file at the repo root that every session reads first: commands, conventions, gotchas. CLAUDE.md in Claude Code.
- **[Progressive disclosure](./progressive-disclosure.md)** — Giving the agent a short index up front and letting it load the detail only when a task calls for it.
- **[Context pointer](./context-pointer.md)** — A short reference that tells the agent where information lives and when to fetch it, instead of the information itself.
- **[Context engineering](./context-engineering.md)** — Deciding what goes into the context window, when, and in what order, so the agent sees what the task needs and nothing else.
- **[Skill](./skill.md)** — A named, reusable procedure the agent loads on demand: a folder of instructions and optional scripts, used when a task matches.
- **[Subagent](./subagent.md)** — A separate agent the main agent spins up for a bounded task, with its own context window; only its final report comes back.

## §07 Patterns of Work

*The working habits that separate a good run from a bad one.*

- **[Human-in-the-loop](./human-in-the-loop.md)** — A working pattern where a person approves, corrects, or answers for the agent while it runs, instead of only judging the result.
- **[AFK](./afk.md)** — Away from keyboard: you start the agent, leave, and come back to finished work you review later instead of supervising live.
- **[Automated check](./automated-check.md)** — A mechanical pass/fail test the harness or CI runs on the agent's work: types, lint, tests, build. Cheap, fast, no judgement.
- **[Automated review](./automated-review.md)** — A model reads the agent's diff and flags problems before a person does: judgement without a human, fuzzier than a check.
- **[Human review](./human-review.md)** — A person reading the agent's work before it ships. The only step that judges whether the change is right, not just whether it passes.
- **[Vibe coding](./vibe-coding.md)** — Building software by describing what you want to an agent and judging the result rather than reading every line of code.
- **[One-shot](./one-shot.md)** — Getting a usable result from a single prompt with no follow-up turns. A good test of a prompt, a bad habit for production.
- **[Design concept](./design-concept.md)** — A short written description of what you're building and why, agreed before any code, so the agent and you share the same picture.
- **[Grilling](./grilling.md)** — Having the agent interview you, question by question, until the requirements are fully resolved before it writes anything.
- **[Prototyping](./prototyping.md)** — Building a quick, throwaway version to learn something, not to keep. With agents it's cheap enough to do before deciding anything.
- **[Harness engineering](./harness-engineering.md)** — Improving the setup around the model (tools, checks, instructions, permissions) so the same model does better work.
- **[DX](./dx.md)** — Developer experience: how pleasant and fast a tool, codebase or workflow is for the humans using it.
- **[AX](./ax.md)** — Agent experience: how well a codebase, tool or environment supports an agent that starts each session knowing nothing.

## Changelog

- **2026-09-12** — Dictionary launched: 81 entries across 7 sections, with tool-specific notes and course links.

---

Missing a word? [Open an issue](https://github.com/dineshxr/vibecodeschool/issues).
⭐ [Star the repo](https://github.com/dineshxr/vibecodeschool) if this saved you a search.
