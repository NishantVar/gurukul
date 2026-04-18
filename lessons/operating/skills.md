---
title: Skills — Reusable Agent Capabilities
created: 2026-04-14
updated: 2026-04-14
track: operating
order: 2
prerequisites:
  - "[[gurukul/lessons/vibing/setting-up-coding-agents]]"
tags:
  - skills
  - automation
  - workflows
content_type: lesson
lesson_format: concept
prompt: "[[gurukul/prompts/operating/skills]]"
---

# Skills — Reusable Agent Capabilities

A **skill** is a reusable capability you give your agent — a set of instructions, a workflow, or any combination — packaged so a single command triggers the whole thing. If you find yourself repeating the same request across sessions, that's the signal: turn it into a skill. One command replaces re-explaining what you want every time, and the agent handles the rest.

## What Changes

Without skills, every session starts from scratch. You re-explain how you want your weekly report structured, re-describe the steps for summarizing meeting notes, re-walk the agent through the same review checklist. The agent does the work fine — but *you* repeat yourself constantly.

**With a skill, you say it once.** After that, one command triggers the whole thing.

## What This Looks Like

You can create a skill by telling your agent what to capture. If you have a `/skill-creator` skill available, it's one line:

```
/skill-creator turn everything we did in this session into a reusable skill
```

The agent reviews your session, extracts the repeatable parts, and packages them into a skill. No manual configuration — just tell it what to capture. If you don't have `/skill-creator`, the same thing works as a plain request: *"Create a reusable skill from what we just did."*

Using that skill later:

```
/my-report-format write up this week's summary
```

Or when the skill hits an edge case and needs fixing:

```
/my-report-format fix the issues we encountered
```

**You customize a skill the same way — just describe what you want.** There are no flags to memorize or settings to configure. You tell the agent what to change in plain language:

```
/my-report-format but this time skip the summary and just give me the action items
```

```
/my-report-format write it up in bullet points instead of paragraphs
```

The skill handles the base workflow. Your words on top steer it. This works because the agent reads both the skill's instructions *and* whatever you add after the command — so every invocation can be different without changing the skill itself.

**Skills aren't static.** You use them, hit a gap, tell the agent to fix it, and the skill gets better. The iteration loop is the same conversation you're already having.

**Invocation syntax varies by tool:**

| Tool | Prefix | Example |
|------|--------|---------|
| Claude Code | `/` | `/my-skill do the thing` |
| Gemini | `/` | `/my-skill do the thing` |
| Codex | `$` | `$my-skill do the thing` |

## How Skills Work

When you create a skill, the agent saves a set of instructions it can find later. **You don't need to manage where it's stored** — the agent handles that when you create or invoke a skill.

There are two kinds:

- **Global skills** apply everywhere — your personal defaults like a formatting preference, a review checklist, or the way you like summaries structured. These follow you across all your projects.
- **Local skills** belong to one project — a specific reporting workflow, team conventions, or processes unique to that project. Anyone working on the project shares them.

If you're comfortable with file paths: global skills live in `~/.claude/skills/` *(or `~/.agents/skills/` for other agent tools)*, and local skills live in `.claude/skills/` *(or `.agents/skills/`)* inside the project folder. If that means nothing to you, don't worry — the agent knows where to put them.

## When to Make One

**Make a skill when you notice repetition** — not when you predict it.

Good candidates:
- A workflow you've repeated across 2–3 sessions
- Instructions you keep re-explaining to the agent
- A multi-step process that needs to happen in a specific order
- Defaults you want applied without asking every time

Skip it when:
- It's a one-off task
- The request changes substantially every time
- The agent already does it well without extra instructions

The test: **if you'd write yourself a sticky note about it, it's a skill.**

## The Over-Engineering Trap

**Don't design skills upfront like software architecture.** You imagine every possible use case, write elaborate instructions, and spend more time maintaining the skill than using it.

**Lazy-load instead.** Automate exactly what's annoying you *right now*. Ship the minimal version. When you hit a gap or something breaks, tell the agent to fix it in that moment. The skill grows from real use, not from speculation about future needs.

This isn't a shortcut — it's the intended workflow. Skills that evolve through use end up matching how you actually work. Skills designed in advance usually don't.

## Try This Now

Think of something you've told your agent more than once this past week — a formatting preference, a way you like summaries written, a review process, anything repetitive.

Tell your agent:

```
/skill-creator turn [that repeated thing] into a reusable skill
```

If nothing comes to mind, try something universal like: *"Create a skill that always formats my meeting notes with an action items section at the top"* — any repeated preference works.

Invoke the new skill on your current work. **If it's not quite right, tell the agent what to fix.** You'll have a working, personalized automation in minutes.
