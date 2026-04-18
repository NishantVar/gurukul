---
title: Setting Up Coding Agents
created: 2026-04-14
updated: 2026-04-14
track: vibing
order: 1
prerequisites: []
tags:
  - setup
  - claude-code
  - coding-agents
content_type: lesson
lesson_format: lab
prompt: "[[gurukul/prompts/vibing/setting-up-coding-agents]]"
---

# Setting Up Coding Agents

Get an AI agent running on your machine and have a real conversation with it — no code, no repositories, no developer background needed. Unlike chatting with AI in a browser, a coding agent can actually *do things* on your computer: read and create files, search the web, install software, and automate tasks. By the end of this lesson, you'll have one set up and working.

## Success State

You have a coding agent installed and running in your terminal. You've given it a plain-English prompt, it responded with something useful, and you're looking at the result. The whole thing took less than 15 minutes.

## The Task

We'll set up **Claude Code** — Anthropic's coding agent. It runs in your terminal and can read/write files, browse the web, run commands, and build things for you.

### Install Claude Code

**If you already have a coding agent** (Cursor, Windsurf, Codex, etc.), tell it:

> Install Claude Code globally using npm.

It will handle the rest. Skip to **Launch it** below.

**If this is your first agent** — a small catch-22: you need to run one terminal command to bootstrap the agent that will handle everything else going forward. Open your terminal (on Mac, search for "Terminal" in Spotlight) and paste:

```
npm install -g @anthropic-ai/claude-code
```

npm is an installer that comes with Node.js (a free program that lets tools like Claude Code run on your computer). If the command fails with "npm: command not found," you need Node.js first — visit [nodejs.org](https://nodejs.org), download the installer, then run the command above again.

### Launch it

Type `claude` in your terminal and press Enter. The first time, it will ask you to sign in with your Anthropic account (a Claude Pro or Max subscription works).

### Give it a prompt

Once Claude Code is running, try this:

> What's the weather like in my city today? Search the web and give me a quick summary.

That's it. Plain English, no special syntax. Claude Code will ask your permission before taking actions (like searching the web) — these are called "tool uses." Say yes when it asks.

## Verify

You should see:
- Claude Code launched without errors
- It searched the web (you approved a permission prompt to let it do this)
- It gave you a weather summary in your terminal

If all three happened, you're set up and working.

## Common Failure Modes

**"command not found: claude"** — The install didn't fully work. Paste the exact error message into [claude.ai](https://claude.ai) or any AI chat and ask it to help you fix the problem. Most likely Node.js didn't install correctly, or your terminal can't find the program yet.

**Sign-in loop or authentication error** — You need an active Claude Pro or Max subscription at [claude.ai](https://claude.ai). Free-tier accounts don't include Claude Code access.

**"Permission denied" during install** — Don't add `sudo` to the command. Instead, paste the error into any AI chat and ask "How do I fix npm global install permissions on Mac without sudo?" It will walk you through it.

## Other Agents

Claude Code is the recommended starting point for this curriculum, but the ideas transfer. Two alternatives if you prefer a different ecosystem:

- **[OpenAI Codex CLI](https://github.com/openai/codex)** — OpenAI's terminal agent. Requires an OpenAI account.
- **[Google Gemini CLI](https://github.com/google-gemini/gemini-cli)** — Google's terminal agent. Requires a Google account.

Both install via npm (check the links above for the exact command) and work the same way: you type a plain-English request, the agent acts, and you approve or guide the result. Once you've used one, switching to another is straightforward — the prompts in this curriculum work with any of them.
