---
lesson: "[[gurukul/lessons/operating/skills]]"
created: 2026-04-14
updated: 2026-04-14
---

## Original Prompt

> Operating - Concept - We need to introduce skills. Basically they are a reusable capability whether it's instructions, scripts, or workflows. If you are going to do something more than once, turn it into a skill. You need to show where the skills are located in your home directory/.agents|.claude/skills; then also locally it can be .agents|.claude/skills. You also need to tell how to invoke a skill. It's / in Claude and Gemini. It's $ in codex. Tell people that they should use /skill creator when they wanna create a skill. I want you to give two examples: 1. /Skill Creator turn everything we did in this session into a reusable skill - This is to show how easy it can be to create a skill. 2. /<skill> fix the issues we encountered - This is how easy it is to fix a skill. Then you need to add a practical tip that they should lazy load skills like whatever you need; automate it and if there are issues or you need more functionality, just add it when you need it.

## Inferred Context

- **content_type**: lesson
- **lesson_format**: concept
- **track**: operating
- **reasoning**: Teaches a single mental model (skills as reusable capabilities). Operating track because it's about the environment around the agent — codified defaults and tool leverage — not just a one-off task. Concept format because the core idea is a principle (turn repetition into skills) with a judgment rule (lazy-load, don't over-engineer).

## Revisions

### 2026-04-14

> One of the very important things you need to show is that it is very easy to execute a skill with custom parameters. Basically change any behavior in the skill by just describing it. You simply have to just explain it.

Applied: Added a "customize by describing" section to "What This Looks Like" — two examples showing how plain language after the skill command steers behavior without changing the skill itself.
