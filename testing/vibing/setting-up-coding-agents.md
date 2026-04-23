---
title: Setting Up Coding Agents
created: 2026-04-20
updated: 2026-04-20
track: vibing
order: 1
prerequisites: []
tags:
  - setup
  - coding-agents
  - claude-code
content_type: lesson
lesson_format: lab
prompt: "[[gurukul/prompts/vibing/setting-up-coding-agents]]"
---

# Setting Up Coding Agents

In about 20 minutes, **the chaos on your desktop will be sorted into folders that actually make sense** — not by you, but by a coding agent running in your terminal that you set up from scratch. By the end you'll see firsthand why people keep saying *"the agent just does it."*

## Why this matters

A coding agent is not a chatbot in a browser tab. **It runs on your machine, can read and write files, and can take actions you approve.** That is the leap. Everything else in this curriculum — better prompts, bigger projects, multi-agent setups — assumes you already have an agent that can touch the real world. This lesson gets you there.

We'll use **Claude Code** as the primary example because it's what we recommend in this curriculum, but **Codex CLI** and **Gemini CLI** work the same way at this level. Pick whichever matches the subscription you already have.

## What you need

- A terminal app (Terminal on Mac, Windows Terminal on Windows, anything on Linux)
- A subscription or account with **at least one** of: Claude (Pro or Max), ChatGPT (Plus or Pro), or a Google account for Gemini *(Gemini has the most generous free tier if you don't want to pay yet)*
- **A desktop you don't mind letting an agent touch**

If you've never opened a terminal before, that's fine — *you'll mostly be typing in plain English once setup is done.* On Mac, press **Cmd+Space**, type "Terminal," hit Enter. On Windows, search for **Terminal** in the Start menu.

## The task

### Step 1 — Install one coding agent

Pick **one** based on which subscription you have. You only need one to do this lesson.

| Tool | Install page |
|------|--------------|
| **Claude Code** *(recommended)* | https://docs.claude.com/en/docs/claude-code/overview |
| **Codex CLI** | https://github.com/openai/codex |
| **Gemini CLI** | https://github.com/google-gemini/gemini-cli |

Each install page has a one-line command to copy into your terminal. Run it, then run the tool's command (`claude`, `codex`, or `gemini`) and follow the prompts to log in with your existing subscription account.

**This is the only time you'll run setup commands by hand.** Once the agent is running, you talk to it in plain English. *(You don't need an API key — your normal subscription login works. An API key is a password-like token developers use to call models programmatically; you don't need one for this.)*

### Step 2 — Launch the agent on your desktop

Start a fresh terminal in your Desktop folder and run `claude` (or `codex` / `gemini`). On Mac you can right-click the Desktop in Finder and pick "New Terminal at Folder." On Windows, open Terminal and type `cd Desktop` before running the tool.

### Step 3 — Ask it to reorganize your desktop

Ask the agent something like:

> My desktop is a mess. Look at what's here and propose a clean folder structure that groups things by category. Don't move anything yet — just show me the plan first.

Read what it suggests. If the grouping looks reasonable, tell it to go ahead. The agent will ask for permission before each batch of file moves — approve them. If anything looks off, say so in plain English ("group by file type instead" or "leave the screenshots alone") and let it adjust.

**Don't point an agent at folders full of irreplaceable files you haven't backed up, and stay away from system folders.** The Desktop is a great first target precisely because it's low-stakes — *you can always drag things back if you don't like the result.*

## Verify

You're done when **all three** of these are true:

1. Running the agent's command (`claude`, `codex`, or `gemini`) opens an interactive prompt in your terminal — not an error.
2. Your desktop has noticeably fewer loose files and a few new folders with sensible names like `Screenshots`, `PDFs`, `Installers`, or `Old Projects`.
3. You can open one of the new folders and recognize why each file landed there.

If any of those isn't true, see the failure modes below.

## Common failure modes

**The install command fails with "command not found" or a permission error.**
Most install commands need either Node.js (for Claude Code) or another runtime already on your machine. The install pages list prerequisites near the top — read those first. On Mac, you may need to run the command with `sudo` or install via Homebrew. *Don't paste random `sudo` commands you don't recognize.*

**The agent says it can't access your desktop or files.**
You probably started it from the wrong folder, or your OS is blocking file access. Quit the agent, run `cd ~/Desktop` again, then restart it. On macOS, your terminal app may need **Full Disk Access** in System Settings → Privacy & Security.

**The agent moves files to weird places or makes a worse mess.**
This happens. Tell it: *"Undo the last set of moves and try again — group by file type instead of by topic."* You can also drag things back manually. **The fix is almost always to give the agent a clearer instruction, not to switch tools.**

## Going further

Once your desktop is clean, try one of these in the same agent session:

- *"Look at my Downloads folder and do the same thing — propose a structure first, then move."*
- *"Find any duplicate files on my desktop and tell me which ones I can safely delete."*
- *"Write a one-paragraph summary of what was on my desktop before you cleaned it up."*

Each of these uses the same pattern: **ask in plain English, review what it proposes, approve the action.** That pattern is the whole foundation of working with coding agents — everything later in this curriculum is just sharper versions of it.
