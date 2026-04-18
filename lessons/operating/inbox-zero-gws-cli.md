---
title: "Inbox Zero with GWS-CLI"
created: 2026-04-17
updated: 2026-04-17
track: operating
order: 3
prerequisites:
  - "[[gurukul/lessons/vibing/mcp-connecting-agents-to-services]]"
  - "[[gurukul/lessons/operating/skills]]"
tags:
  - gmail
  - cli
  - automation
  - google-workspace
content_type: lesson
lesson_format: project
prompt: "[[gurukul/prompts/operating/inbox-zero-gws-cli]]"
---

# Inbox Zero with GWS-CLI

Right now, your agent can't touch your email. After this project, **your agent manages your Gmail directly** — and **the filters keep working permanently**, so your inbox stays clean without you thinking about it. You'll also learn a second way to connect your agent to external services — **CLI tools** — which works for any command-line program, not just Google.

## What You're Building

A Gmail system where incoming emails from known senders — newsletters, notifications, receipts, social updates, marketing — get automatically labeled and archived the moment they arrive. Your inbox only shows messages that genuinely need your attention. The agent has permanent access to your Gmail through GWS-CLI, so you can ask it to manage email anytime, not just during this project.

## What You'll Need

- **GWS-CLI** — Google's official command-line tool for Workspace ([github.com/googleworkspace/cli](https://github.com/googleworkspace/cli)). Your agent will install it during the build.
- A Google account you want to organize

## The Build

### 1. Connect Your Agent to Google Workspace

You already know MCP as one way to give your agent access to external services. **CLI tools are a second way.** A **CLI** *(command-line interface)* is a program you control by typing text commands instead of clicking buttons — your agent can run these commands directly. Here's how the two approaches compare:

| | MCP Server | CLI + Skill File |
|---|---|---|
| **Setup** | Install server, configure protocol | Install the tool, add a skill file |
| **How it runs** | Always on in the background | Runs only when your agent calls it |
| **Works for** | Services with MCP adapters | Any tool with a command-line interface |
| **Examples** | Filesystem, database, Notion | `gws` (Google), `gh` (GitHub), `stripe` |

**Any CLI tool can become an agent capability this way**: install it, write (or reuse) a skill that explains the commands, and your agent can use it. MCP and CLI aren't competing — they're two options, and some services only offer one or the other.

GWS-CLI ships with a command that generates skill files automatically. Ask your agent:

> Install GWS-CLI from github.com/googleworkspace/cli. Once it's installed, run `gws generate-skills` to create skill files that teach you how to use it. Then add a section to my CLAUDE.md (or agent instructions) that tells you where the skill files are, so you can read them whenever I ask about Google Workspace.

When it's done, confirm that your agent instructions — *the persistent instruction file (like CLAUDE.md) that tells your agent how to behave across sessions* — now mention GWS-CLI and skill files. That's the entire integration.

**Authentication is the one step you do yourself.** GWS-CLI needs permission to access your Google account, and that requires you to sign in through a browser — *your agent can't click through a Google login screen for you*. Ask your agent what command to run, then run it in your terminal (the Terminal app on Mac, Command Prompt or PowerShell on Windows). It will open a browser window where you sign in and grant permissions. This is a one-time step per account.

**Verify:** Ask your agent to show your unread inbox using GWS-CLI. You should see a table of recent unread emails — sender, subject, and date.

### 2. Download Your Inbox

Now pull down the basic info — sender, subject, date — for everything unread. Anything older than three months is unlikely to need action — safe to ignore or archive in bulk later.

> Use GWS-CLI to list all my unread emails from the last 3 months. For each email, capture the sender, subject, and date. Save everything to a data file called inbox-dump. Make sure to fetch all results, not just the first page.

**Verify:** Ask the agent how many emails it captured and to show you 5 random samples. Spot-check them against your actual inbox.

### 3. Find the Patterns

This is where the agent earns its keep. You have a pile of email metadata — let it find the structure.

> Analyze the inbox-dump file and group the emails by sender domain (the part after the @ in the email address — like amazon.com or linkedin.com). Show me:
> - The top 15 sender domains (e.g. amazon.com, linkedin.com) by volume
> - For each domain, a few example subjects so I can tell what kind of email it is
> - Suggested label categories (like Newsletters, Notifications, Receipts, Social, Marketing)
>
> Present this as a table I can review before we act on it.

Review the output. You're looking for categories that make sense for *your* inbox. Common patterns:

| Category | Typical senders |
|----------|----------------|
| Newsletters | Substack, Medium, industry blogs |
| Notifications | GitHub, Jira, Slack digests |
| Receipts | Amazon, banks, payment services |
| Social | LinkedIn, Twitter/X, Facebook |
| Marketing | SaaS products, retail, deal sites |

Adjust the categories to match your reality. Merge small groups, split large ones, rename anything that feels wrong. **The agent suggested categories — you decide which ones to keep.**

### 4. Create Labels and Filters

Once you've settled on categories, the agent builds the Gmail infrastructure.

> For each of these categories, create a Gmail label using GWS-CLI. Then create a Gmail filter for each category that matches the sender domains we identified. Each filter should:
> - Apply the matching label
> - Archive the message (remove it from the inbox)
>
> Here are my final categories and their sender domains:
> - Newsletters: [list the domains from the analysis]
> - Notifications: [list the domains]
> - Receipts: [list the domains]
> - [add your other categories]

**Filters apply to all future incoming mail** — every new email matching a filter gets labeled and archived without you touching it.

**Verify:** Ask the agent to list your Gmail labels and filters to confirm everything was created correctly.

### 5. Clean the Backlog

**Filters only catch future emails.** Your existing inbox needs a one-time cleanup.

> For each category we just created, find all matching emails currently in my inbox using GWS-CLI. Apply the category label and archive them. Process one category at a time and tell me how many emails you moved for each.

This is the payoff. Hundreds of emails getting labeled and archived in seconds, leaving behind only the messages that don't match any pattern — the ones that actually need your attention.

**Verify:** Ask the agent to show your inbox again. It should be dramatically shorter. Everything that remains is something no filter caught — either genuinely important or a new pattern to add later.

## Verify It Works

Send yourself a test email from an address that matches one of your filters, or wait for a real one to arrive. Then:

> Show my current inbox with GWS-CLI. Also check if any emails arrived in the last hour that got auto-labeled and archived.

The filtered email should not appear in your inbox. It should be archived with the correct label applied. If you check Gmail's web interface, you'll find it under the label — sorted, not lost.

## What Can Go Wrong

| Problem | Fix |
|---------|-----|
| Authentication fails or expires | Re-run the auth command (ask your agent for it). Login tokens expire periodically — this is normal |
| "Too many requests" errors during bulk operations | Gmail limits how many requests you can make per minute. Ask the agent to add short delays between requests or process in smaller batches |
| Filter not catching some emails | Ask your agent to check the filter criteria. Filters matching an entire domain (like @amazon.com) catch more than filters matching a single address. Ask the agent to broaden any filters that are too narrow |
| Labels created but backlog cleanup missed some | The search might have been too narrow. Ask the agent to look for all matching emails in your inbox — including ones you've already read — and archive those too |
| Wrong emails archived | Easy to undo. Ask the agent to find all messages with a specific label and move them back to the inbox |

## Make It Yours

**Add new patterns over time.** Run the dump-and-analyze process again in a month. New senders will have appeared, and you might spot categories worth splitting. The whole workflow is repeatable.

**Schedule regular triage.** Ask your agent to show your inbox at the start of each work session. With filters handling the noise, the unread list becomes a genuine priority queue instead of a wall of notifications.

**Apply the CLI pattern to other tools.** The install-then-skill-file approach works for any command-line tool. For example, with `gh` (GitHub's CLI): install it, write a skill file covering `gh issue list`, `gh pr create`, etc., and your agent can triage GitHub issues the same way it triages email.

**Multiple accounts.** GWS-CLI supports more than one Google account through separate configurations. Ask your agent to set up a second config directory, authenticate it, and update your agent instructions so you can say "triage my work email" vs. "triage my personal email." Then run this entire inbox zero workflow on the second account.
