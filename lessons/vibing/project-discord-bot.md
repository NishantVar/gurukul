---
title: "Project: Discord Bot Setup"
created: 2026-04-14
updated: 2026-04-18
track: vibing
order: 6
prerequisites:
  - "[[gurukul/lessons/vibing/setting-up-coding-agents]]"
  - "[[gurukul/lessons/vibing/browser-automation]]"
  - "[[gurukul/lessons/vibing/mcp-connecting-agents-to-services]]"
tags:
  - discord
  - mcp
  - browser-automation
  - project
content_type: lesson
lesson_format: project
prompt: "[[gurukul/prompts/vibing/project-discord-bot]]"
---

# Project: Discord Bot Setup

By the end of this project, your coding agent will be able to interact with The New Order Discord server — **send messages, read conversations, list channels, and more** — all because you asked it to in plain English. You'll create your own personal Discord bot, connect it to your agent, and be able to participate in the server through your coding agent.

## What You're Building

A Discord bot connected to your coding agent through MCP *(the protocol from the [[gurukul/lessons/vibing/mcp-connecting-agents-to-services]] lesson)*. Here's the setup:

```
You → Coding Agent → Discord MCP Server → The New Order Server
```

When you're done, conversations like this will work:

| You say | What happens |
|---------|-------------|
| "Post a message in #bots saying hi" | Agent sends the message as your bot |
| "What were the last 5 messages in #bots?" | Agent reads and summarizes them |
| "List all the channels on the server" | Agent shows you the full channel list |
| "Who's in the server right now?" | Agent checks the member list |

**The bot is the bridge** — it lives on The New Order server and gives your agent permission to interact there. You'll create it using browser automation *(your agent handles the Discord website for you)*, then wire it up with MCP so your agent treats Discord as a native tool.

**When this is the right approach:** You want your agent to interact with a Discord server on your behalf through conversation — posting, reading, exploring. *If you're building a public bot that responds to events automatically (reaction roles, welcome messages triggered by joins), you'd eventually need a traditional bot framework. If you just want notifications sent to a channel, a simple webhook is even easier.* This project gives you the most versatile starting point: **your agent can do anything on Discord that the bot has permission to do.**

**The pattern transfers.** This same approach — browser automation to set up credentials on a service's website, then MCP to give your agent permanent access — works for GitHub, Notion, Slack, and other services that have MCP servers available. *Discord is the example; the method is general.*

## What You'll Need

- A Discord account — if you don't have one, create one at discord.com
- You must be a member of **The New Order server** — you'll be adding your bot to this server
- The browser-automation lesson completed — your agent needs agent-browser installed *(see [[gurukul/lessons/vibing/browser-automation]])*

## The Build

### Step 1: Log into the Discord Developer Portal

Discord requires you to create a **"bot application"** on their developer website before anything else. Your agent will open this site for you using browser automation — but since it needs your login, the browser opens visibly on your screen so you can type your password.

> Open https://discord.com/developers/applications using agent-browser with a visible browser window. Take a snapshot when the page loads.

A browser window will appear. **If you see a login page, log in yourself** — your agent can't and shouldn't type your password. Once you're logged in and see the Applications dashboard, tell your agent:

> Take a snapshot of the page now.

**Verify:** Your agent confirms it can see the Applications dashboard.

### Step 2: Create the bot application

A **"bot application"** is Discord's name for a bot identity — the thing that will join your server and act on your agent's behalf.

> Create a new application called "[Your Name] Bot" on this page.

Use your actual name — for example, "Alex Bot" or "Sarah Bot". **This is how your bot will appear on the server,** so everyone knows whose agent is posting.

Your agent figures out how to navigate the creation flow. When it's done, you'll land on the new application's settings page.

**Verify:** Ask your agent to snapshot the page. You should see your bot's name as the application name.

### Step 3: Get the bot token and enable message reading

Now your agent needs two things from the Bot settings: a **token** *(a secret key that lets your agent control this bot — treat it like a password)* and a permission called **Message Content Intent** *(which lets the bot read what people write, not just see that messages exist)*.

> Go to the Bot section, generate a new bot token, and show it to me. Also enable Message Content Intent in the Privileged Gateway Intents settings.

**Copy the token and save it somewhere safe** — a note, a password manager, anywhere you won't lose it. *Discord only shows it once. If you lose it, you'll have to generate a new one.*

**Verify:** Your agent shows you a long string of characters (the token) and confirms Message Content Intent is enabled.

### Step 4: Invite the bot to your server

The bot exists on Discord's side, but **it hasn't joined your server yet.** Your agent will generate an invite link with the permissions it needs and use it.

> Generate an invite URL for this bot with Send Messages, Read Message History, and View Channels permissions, then open it and add the bot to The New Order server.

**These permissions let the bot read and post in channels — which is all you need for this project.** When the invite page asks which server to add the bot to, make sure you select **The New Order**.

*You may need to complete a CAPTCHA yourself in the browser window — that's one thing the agent can't handle for you.*

**Verify:** Open Discord normally and check The New Order's member list. You should see your bot listed by the name you chose *(it'll show as offline — that's normal and explained below)*.

### Step 5: Connect the bot to your agent via MCP

Close the browser — the website work is done. Now your agent wires the bot into its own configuration so it can use Discord as a tool.

> Set up a Discord MCP server in my coding agent's configuration using this bot token: [paste your token here]

Your agent handles finding the right config file and writing the correct format. *If your agent asks which MCP server package to use, tell it to search for a maintained Discord MCP server — there are several available, and your agent can evaluate which one supports the tools you need. If the first one doesn't work, ask your agent to try a different package.*

**Verify:** Restart your coding agent session *(close and reopen it)*, then ask:

> List all your available MCP tools that mention "discord".

You should see a list of tools — things like `send_message`, `list_channels`, `create_role`, and many more. **If these appear, the connection is live.**

## Verify It Works

End-to-end test — paste this:

> Send a message in the #bots channel on The New Order Discord server that says "Hello from [your name]'s coding agent! Bot setup complete."

**Open Discord and check #bots on The New Order.** If the message is there, posted by your bot, everything is working. Try one more:

> List all the channels on The New Order server.

Your agent should return the full channel list. **You're now interacting with The New Order through plain conversation.**

## What Can Go Wrong

**"Token is invalid" or "401 Unauthorized"**
The most common issue. The token was copied with extra spaces, missing characters, or a newline. Ask your agent: "Show me the bot token in the MCP config." **Compare it with what Discord showed you and fix any differences.**

**"Missing Access" or "403 Forbidden"**
The bot doesn't have permission in that specific channel. Either the channel has a permission override that blocks your bot, or it needs an additional permission you didn't include in Step 4. Ask your agent: "Check what permissions my bot has on this server." *If the bot is missing a permission, go back to Step 4 and re-invite it with the correct permissions — the new invite will update the existing bot's permissions.*

**Browser automation fails or times out**
Discord's website loads dynamically and can be slow. Tell your agent: **"Wait a few seconds, take a new snapshot, and try again."** *Browser automation on complex sites sometimes needs a second attempt.*

**No Discord tools after setup**
**You need to restart your agent session after adding MCP configuration.** Close and reopen your coding agent, then check for tools again.

**Bot shows offline in Discord**
Normal. **MCP-connected bots make API calls on demand rather than staying permanently connected.** The bot works even though it looks offline — test it with the verification step above.

## Make It Yours

- **Fetch lessons without opening Discord:** Your bot can pull any lesson directly from the server. Ask your agent: "Get the latest lesson from The New Order Discord." **You don't need to open Discord or post anything** — the bot reads the lesson channels and brings the content to you. Try this for the next lesson that drops — read it right from your coding agent instead of switching to Discord.
- **Catch up on conversations:** "Summarize what's been happening in #bots today." Your agent reads and condenses the messages so you can catch up without scrolling.
- **Explore the server:** "What channels exist on The New Order and what are they about?" Get a quick overview of the server layout through your agent.
- **Post from your agent:** "Send a message in #bots asking if anyone wants to pair up on the next project." Your bot posts on your behalf — *everyone sees it's from your named bot.*
