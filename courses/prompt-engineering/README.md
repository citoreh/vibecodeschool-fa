<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported. -->

# Prompt Engineering Mastery

> Every technique that matters in 2026 — from zero-shot to chain-of-thought to prompt injection defense.

The complete prompting curriculum: foundations, reasoning techniques, reliability, structured output, image and multimodal prompting, and the security layer — prompt hacking and how to defend against it. 35 lessons, every one hands-on, every technique tested against current frontier models.

| | |
|---|---|
| **Level** | Beginner |
| **Lessons** | 35 across 6 modules |
| **Time** | ~24 hours |
| **Cost** | Free · no signup |
| **Take it interactively** | [https://vibecodeschool.com/courses/prompt-engineering](https://vibecodeschool.com/courses/prompt-engineering) |

Every lesson below links to its interactive version — steps you run locally,
scrubbable agent-session replays, and a quiz that gates completion.

## Module 1 — Prompting Foundations

The working parts of a prompt — precise instructions, delimiters, roles, and examples — assembled into contracts that hold up under real input.

- **[What Prompt Engineering Actually Is](https://vibecodeschool.com/learn/pe-01-what-is-prompt-engineering)** · Concept · 9 min
  Prompting is interface design for a probabilistic machine — you arrange context so the output you want becomes the most likely continuation.
- **[Anatomy of a Prompt](https://vibecodeschool.com/learn/pe-02-anatomy-of-a-prompt)** · Concept · 10 min
  Role, instruction, context, input data, output format — the five working parts of a prompt, and why their order changes behavior.
- **[Instructions & Constraints](https://vibecodeschool.com/learn/pe-03-instructions-and-constraints)** · Walkthrough · 14 min
  Turn vague asks into precise instructions with positive constraints, hard delimiters, and an output contract that survives hostile input.
- **[Role Prompting](https://vibecodeschool.com/learn/pe-04-role-prompting)** · Concept · 9 min
  Personas change vocabulary, framing, and priorities — not capability. When a role earns its tokens and when it's superstition.
- **[Zero-Shot, One-Shot, Few-Shot](https://vibecodeschool.com/learn/pe-05-zero-one-few-shot)** · Walkthrough · 14 min
  Dial examples from zero to few and watch behavior lock in — plus how example choice, balance, and order quietly steer the model.
- **[Combining the Basics](https://vibecodeschool.com/learn/pe-06-combining-basics)** · Sandbox replay · 16 min
  Watch a vague classifier prompt become production-grade: label space, output contract, few-shot edge cases, and a hostile-input test.

## Module 2 — Reasoning Techniques

Make models show and improve their work: chain-of-thought, decomposition, voting across samples, and where 2026 reasoning models change the playbook.

- **[Chain-of-Thought Prompting](https://vibecodeschool.com/learn/pe-07-chain-of-thought)** · Concept · 10 min
  Showing worked reasoning before the answer makes multi-step tasks dramatically more reliable — when the task actually has steps.
- **[Zero-Shot CoT & Step-by-Step Triggers](https://vibecodeschool.com/learn/pe-08-zero-shot-cot)** · Walkthrough · 13 min
  Trigger reasoning without examples, structure the scratchpad, and extract clean final answers your code can parse.
- **[Self-Consistency](https://vibecodeschool.com/learn/pe-09-self-consistency)** · Concept · 9 min
  Sample several reasoning paths and let them vote — buying accuracy with compute on tasks that have a checkable final answer.
- **[Decomposition: Least-to-Most & Subproblems](https://vibecodeschool.com/learn/pe-10-decomposition-least-to-most)** · Walkthrough · 14 min
  Break a hard task into ordered subquestions, solve them one by one, and feed each answer forward — reasoning as a pipeline, not a leap.
- **[Generated Knowledge & Prompt Priming](https://vibecodeschool.com/learn/pe-11-generated-knowledge-priming)** · Concept · 10 min
  Have the model write down relevant facts before answering — surfacing latent knowledge into context, where it constrains the answer.
- **[Reasoning Models vs CoT Prompts](https://vibecodeschool.com/learn/pe-12-reasoning-models-vs-cot)** · Concept · 11 min
  Extended-thinking models do CoT natively — what that retires, what it doesn't, and how to split work between fast and thinking modes.

## Module 3 — Reliability & Truthfulness

Why models fabricate, and the countermeasures that ship: calibrated abstention, critique loops, ensembles, debiasing, and prompt test sets.

- **[Why Models Hallucinate](https://vibecodeschool.com/learn/pe-13-why-models-hallucinate)** · Concept · 10 min
  Fluency is probability, not truth — the mechanics of confident fabrication, and a taxonomy that tells you which fix fits which failure.
- **[Calibration: Getting 'I Don't Know'](https://vibecodeschool.com/learn/pe-14-calibration-and-uncertainty)** · Walkthrough · 14 min
  Give the model permission, vocabulary, and incentive to say 'I don't know' — abstention rules, confidence labels, and source-bound answers.
- **[Self-Critique & Revision Loops](https://vibecodeschool.com/learn/pe-15-self-critique-loops)** · Walkthrough · 14 min
  Draft, critique against a rubric, revise — and the tricks (fresh context, forced findings) that stop self-review from rubber-stamping.
- **[Prompt Ensembling & Voting](https://vibecodeschool.com/learn/pe-16-prompt-ensembling)** · Concept · 10 min
  Ask several ways, let the answers vote — prompt variants, format mixes, and cross-model panels that catch what any single prompt misses.
- **[Order Effects & Debiasing](https://vibecodeschool.com/learn/pe-17-debiasing-and-ordering)** · Concept · 10 min
  Position boosts, majority-label leaks, and recency pulls — the ordering biases in prompts and judges, and the habits that neutralize them.
- **[Testing Prompts Like Code](https://vibecodeschool.com/learn/pe-18-testing-prompts-like-code)** · Walkthrough · 15 min
  A 20-case test set, a scoreboard, and a regression rule — the smallest setup that turns prompt edits from vibes into engineering.

## Module 4 — Structured Output & Production Prompting

Prompts that survive production — strict output contracts, long-context and RAG patterns, agent system prompts, meta-prompting, and versioning.

- **[Output Contracts: JSON, Schemas, Delimiters](https://vibecodeschool.com/learn/pe-19-output-contracts-json-schemas)** · Walkthrough · 14 min
  Turn 'usually valid JSON' into valid, typed data — schemas, delimiters, and validate-then-repair as a real output contract.
- **[Long-Context Prompting](https://vibecodeschool.com/learn/pe-20-long-context-prompting)** · Concept · 10 min
  Placement, labeling, and quote-then-answer — how to prompt reliably when the context is huge and attention isn't uniform.
- **[RAG Prompting Patterns](https://vibecodeschool.com/learn/pe-21-rag-prompting-patterns)** · Concept · 11 min
  Grounding, citations, and a scripted no-answer — the prompt patterns that make retrieval-augmented generation trustworthy.
- **[Prompting AI Agents](https://vibecodeschool.com/learn/pe-22-prompting-ai-agents)** · Concept · 11 min
  System prompts for tool-using agents: tool descriptions, stop conditions, and guardrails a chat prompt never needed.
- **[Meta-Prompting: AI That Writes Prompts](https://vibecodeschool.com/learn/pe-23-meta-prompting)** · Walkthrough · 14 min
  Use a strong model to draft, critique, and repair your prompts — and know the cases where hand-tuning still wins.
- **[Prompt Versioning & Model Migration](https://vibecodeschool.com/learn/pe-24-prompt-versioning-and-migration)** · Concept · 10 min
  Prompts are code: version them, changelog them, A/B them against a fixed test set, and migrate them safely across models.

## Module 5 — Image & Multimodal Prompting

Prompt beyond text — generating images with control, steering with negatives and weights, reading images as input, and the voice and video frontier.

- **[Text-to-Image Prompting Basics](https://vibecodeschool.com/learn/pe-25-text-to-image-basics)** · Concept · 10 min
  The anatomy of an image prompt — subject, medium, style, composition, lighting — and an iteration workflow across 2026's tools.
- **[Style Modifiers & Quality Boosters](https://vibecodeschool.com/learn/pe-26-style-modifiers-quality-boosters)** · Walkthrough · 15 min
  Build one base prompt into a controlled result by layering medium, style, lighting, lens, and render terms — then save the recipe.
- **[Negative Prompts & Weighted Terms](https://vibecodeschool.com/learn/pe-27-negative-prompts-and-weighting)** · Concept · 9 min
  Excluding elements, the tool-specific syntax for emphasis, and the predictable ways negatives and weights fail.
- **[Prompting With Images as Input](https://vibecodeschool.com/learn/pe-28-prompting-with-images-as-input)** · Walkthrough · 15 min
  Vision prompting that ships: screenshots to bug reports, charts to data, photos to JSON — grounded and few-shot.
- **[Voice, Video & Multimodal Frontiers](https://vibecodeschool.com/learn/pe-29-voice-video-multimodal)** · Concept · 10 min
  Realtime voice, video understanding and generation, and cross-modal chains — where the prompting fundamentals still apply.

## Module 6 — Prompt Hacking & Defense

The security layer every builder needs — how prompt injection, jailbreaks, and prompt leaking work, and how to defend your own app in depth.

- **[Prompt Injection](https://vibecodeschool.com/learn/pe-30-prompt-injection)** · Concept · 11 min
  The #1 LLM app risk: how untrusted text becomes instructions, direct versus indirect, and the incident patterns to expect.
- **[Jailbreaking: A Taxonomy](https://vibecodeschool.com/learn/pe-31-jailbreaking-taxonomy)** · Concept · 10 min
  The main jailbreak classes as concepts — role-play, obfuscation, many-shot, crescendo — and why defense must be layered.
- **[Prompt Leaking & System Prompt Extraction](https://vibecodeschool.com/learn/pe-32-prompt-leaking)** · Concept · 9 min
  Why 'please don't reveal this' fails, and how to design a system prompt that's safe to leak in the first place.
- **[Defense in Depth for LLM Apps](https://vibecodeschool.com/learn/pe-33-defensive-prompting)** · Walkthrough · 16 min
  Stack the layers — spotlighting, instruction hierarchy, sandwich, output filtering, least-privilege tools — into a defended prompt.
- **[Red-Teaming Your Own App](https://vibecodeschool.com/learn/pe-34-red-teaming-your-app)** · Walkthrough · 15 min
  Build an attack suite for YOUR app, score its block rate, fix the failures, and regression-test your defenses in CI.
- **[Capstone: Your Prompt Playbook](https://vibecodeschool.com/learn/pe-35-capstone-prompt-playbook)** · Walkthrough · 16 min
  Assemble everything into a living playbook: five task templates, a test set, a defense checklist, and a migration log.

---

⭐ Useful? [Star the repo](https://github.com/dineshxr/vibecodeschool) and [start the course free](https://vibecodeschool.com/courses/prompt-engineering).
