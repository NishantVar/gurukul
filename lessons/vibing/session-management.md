---
title: Session Management
created: 2026-04-14
updated: 2026-04-15
track: vibing
order: 4
prerequisites:
  - "[[gurukul/lessons/vibing/setting-up-coding-agents]]"
tags:
  - sessions
  - claude-code
  - workflow
content_type: lesson
lesson_format: lab
prompt: "[[gurukul/prompts/vibing/session-management]]"
---

**Anytime you need to get something digital done, ask your coding agent.** Even if you could do it yourself faster this one time, doing it through the agent means you have a record. Next time you need the same thing, you just say "do it again." This lab shows you how to find and reuse those past sessions in Claude Code. Every agent saves sessions — Codex CLI, Gemini CLI, and others all do this — but the commands differ, so we'll focus on Claude Code here. *(If you use another agent, check its docs for equivalent commands.)*

## Success State

You can resume a previous Claude Code session, and ask the agent to repeat or build on what it did before.

## The Why

The more you use your agent, the more valuable your session history becomes. A week from now you won't remember exactly how you set something up — but the agent's session log has every step. **The agent already knows what it did. You just have to get back to the right conversation.**

## The Task

### 1. Name sessions worth finding later

Claude Code auto-generates session titles, and you can usually find what you need by scanning the list. But if you know a session is one you'll want to come back to, **rename it** so it stands out:

```
/rename setting up the blog
```

Type this inside an active session and it gets a clear, searchable name instead of an auto-generated one. This isn't required — the default titles work fine for most sessions — but it makes your important ones easy to spot when you're browsing later.

### 2. Extend your session retention

Claude Code deletes old sessions after 30 days by default. That's too short — you'll lose useful sessions before you need them again. Ask your agent to increase it:

> "Change my session expiration to 90 days"

Three to six months is a good range. The storage cost is negligible, and a session you ran two months ago can save you an hour of re-explaining.

### 3. Continue your last session

Close Claude Code and reopen it with:

```
claude --continue
```

This **picks up exactly where your last conversation left off.** The full history is there — the agent knows what it did, what you asked for, and what the result was.

Try asking a follow-up, like "do that again" or "change X about what you just did." The agent knows what "that" refers to because it can see the whole session.

### 4. Browse your session history

Close Claude Code again and run:

```
claude --resume
```

This shows a list of your past sessions. Each one has a title and timestamp. Scroll through, pick one, and you're back in that conversation with full context.

### 5. Repeat past work

Once you've resumed an older session, ask the agent to redo or modify what it did. For example:

- "Do that again but for a different file"
- "Run the same thing but change the name to X"
- "Update what you wrote last time to also handle Y"

**This is the payoff.** The second time is almost free — the agent already knows the approach, the files, and the context. You're not re-explaining anything.

## Common Failure Modes

**"I don't see any past sessions"**
You need at least one previous session. Run any task in Claude Code first, then try `--resume` again.

**"The agent doesn't remember what I asked"**
You probably started a fresh session instead of resuming one. **A plain `claude` command starts blank.** Use `--continue` or `--resume` to get back into a previous conversation.

**"I have too many sessions and can't find the one I want"**
The `--resume` list shows sessions by recency with titles based on what you discussed. If you remember roughly what you were working on, scan the titles. Over time you'll naturally develop a habit of starting new sessions for new tasks, which keeps things findable.

**"The agent seems to have forgotten the beginning of a long session"**
Very long sessions can hit the agent's memory limit, causing it to lose the earliest messages. If that happens, start a fresh session and briefly summarize what you need from the old one.

