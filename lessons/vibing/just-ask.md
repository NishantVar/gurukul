---
title: Just Ask
created: 2026-04-14
updated: 2026-04-15
track: vibing
order: 2
prerequisites:
  - "[[gurukul/lessons/vibing/setting-up-coding-agents]]"
tags:
  - prompting
  - getting-started
content_type: lesson
lesson_format: lab
prompt: "[[gurukul/prompts/vibing/just-ask]]"
---

# Just Ask

Your coding agent can figure things out for you. **Not just write code — research questions, find tools, explain options, and tell you what to do next.** Most of the time, getting something done starts the same way: you describe what you want in plain language.

This lab proves that with a real example.

## The task

Open your coding agent and type:

> Search online and tell me how I can control my Gmail from my coding agent.

**That's the whole prompt.** Don't add instructions about format, structure, or which tools to use. Just ask.

Read what comes back. The agent will search the web, find relevant information, and explain your options — likely mentioning specific tools and methods for connecting email to a coding agent. **The details matter less than the experience:** you asked something you didn't know, and got a useful answer without doing any legwork.

## Verify

Your result checks out if:

- The agent gave you a **specific** answer *(named real tools, methods, or services — not just "you can use an API")*
- The answer includes enough detail that you could take a **next step** if you wanted to
- **You didn't have to look anything up yourself** to get the answer

To verify the answer is trustworthy, *not just confident-sounding*, pick one claim from the response — a tool name, a service, a method — and ask:

> Is [thing the agent mentioned] real? Where can I find its official documentation?

If the agent confirms it with a real link or source, the original answer checks out. **If it backtracks or can't find a source, you just learned something equally valuable: spot-check before you act.**

## Common failure modes

**The agent doesn't search the web.** Some agents need web search turned on. If yours says "I don't have access to the internet" or gives a vague answer without citing anything, check your agent's settings for web search or internet access. *In Claude Code, web search works out of the box. Other tools may need a toggle or plugin.*

**The answer is too generic.** If you get something like "you could use the Gmail API," that's not specific enough. Follow up: **"Be more specific — what exactly would I install or set up to make this work?"** Agents respond to pushback. *A weak first answer doesn't mean the agent can't help; it means you should ask again with more focus.*

**You're tempted to Google it first.** That's the habit this lab breaks. **Your agent can search, read, and summarize for you.** Let it.
