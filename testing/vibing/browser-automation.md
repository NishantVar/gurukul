---
title: Browser Automation
created: 2026-04-14
updated: 2026-04-14
track: vibing
order: 7
prerequisites:
  - "[[gurukul/lessons/vibing/setting-up-coding-agents]]"
tags:
  - browser-automation
  - agent-browser
  - tools
content_type: lesson
lesson_format: lab
prompt: "[[gurukul/prompts/vibing/browser-automation]]"
---

# Browser Automation

Your coding agent can also control a web browser — open pages, click buttons, fill forms, read content. You type a request in plain English, and the agent does the browsing for you. This turns any website into something your agent can work with, even when there's no other way to get the data.

## What "Done" Looks Like

Your agent opens a real website in a browser, reads what's on the page, and reports back specific information it found — all without you touching a browser yourself.

## Why This Matters

Imagine you want to check the top stories on five news sites every morning, or track prices on a dozen product pages, or pull contact info from a list of company websites. Doing that by hand means opening each site, finding the info, and copying it — every time. With browser automation, you ask your agent once and it does the clicking, reading, and reporting for you.

Browser automation works best on public pages with straightforward content. Sites that require login, use CAPTCHAs, or load content through complex interactions are harder — still possible, but you'll hit friction. For this lesson, we're starting with the easy case: reading a public page.

## The Task

You'll use a tool called **agent-browser** — a package that gives your agent the ability to control a browser. Your agent installs it and uses it automatically; you just ask for what you want.

Paste this into your coding agent:

> Install agent-browser, then open https://news.ycombinator.com, take a snapshot of the page, and tell me the top 5 story titles.

A "snapshot" means the agent reads the page as structured text — not a screenshot, but a list of what's on the page: headings, links, buttons, text. Think of it like the agent scanning the page and listing everything it can see and interact with. Your agent handles the rest: it installs agent-browser, launches a real browser in the background (no window pops up, but JavaScript runs and pages load fully), navigates to Hacker News, reads the snapshot, and reports back the headlines.

## Verify

You should get back 5 real Hacker News headlines — current ones, not made-up examples. Open Hacker News in your own browser and check that the titles match.

## Common Failure Modes

**"Chrome/Chromium not found"**
Ask your agent: "Run agent-browser install to download a browser for automation." It'll grab a dedicated copy that won't touch your regular browser.

**The snapshot comes back empty or garbled**
Some pages load content dynamically after the initial load. Ask your agent: "Open the page, wait for it to fully load, then take the snapshot." That gives the page time to finish rendering.

**"Command not found: agent-browser"**
Ask your agent: "Verify that agent-browser is installed correctly and reinstall it if it isn't." This is usually a setup hiccup your agent can sort out on its own.

## What You Need

- Node.js installed (if you're not sure, ask your agent "Do I have Node.js installed?")
- No browser setup required — agent-browser handles its own browser

## Going Further

A few things to try next:

- **Screenshot a page**: "Take a screenshot of [any URL] and show it to me"
- **Fill a form**: "Open [URL], snapshot the page, and fill in the search box with 'AI agents'"
- **Extract data**: "Open [URL], snapshot it, and pull out all the links on the page"

Each of these follows the same pattern: open, snapshot, interact, re-snapshot. That cycle — navigate, read, act, verify — is the core loop of all browser automation. This lesson uses agent-browser, but the pattern is the same regardless of which browser automation tool your agent uses. The skill is knowing what to ask for, not which tool runs under the hood.
