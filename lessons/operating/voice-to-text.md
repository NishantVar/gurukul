---
title: Voice to Text — Talk Instead of Type
created: 2026-04-14
updated: 2026-04-14
track: operating
order: 1
prerequisites:
  - "[[gurukul/lessons/vibing/setting-up-coding-agents]]"
tags:
  - voice
  - productivity
  - tools
content_type: lesson
lesson_format: lab
prompt: "[[gurukul/prompts/operating/voice-to-text]]"
---

# Voice to Text — Talk Instead of Type

Talk to your computer instead of typing and get accurate text in any app — prompts, messages, notes, code comments, everything. You'll set up Wispr Flow, which runs system-wide so it works wherever you can type.

## Why this matters

Before: you think of what to tell your agent, then spend time typing and editing it into a clean sentence — the typing is the bottleneck, and you self-censor along the way. After: you press a key, say what you're thinking, and the text appears. **Voice is roughly 3x faster than typing**, but the real shift is that you can ramble — think out loud, change direction mid-sentence, let the tool capture everything. **You build at the speed of your thought instead of the speed of your fingers.**

## When to talk vs. type

**Voice wins when you're composing anything longer than a sentence** — prompts, explanations, braindumps, messages. The longer the thought, the bigger the speed advantage. Voice also wins when you're not sure what to say yet, because rambling into a mic is faster than staring at a blinking cursor.

**Type when you need exact syntax:** file paths, variable names, code, URLs. Autocorrect fights you on these. Also type when you're in a noisy room or a library — voice needs a baseline of quiet and privacy to work well.

**Rule of thumb: if you'd normally pause to think about how to phrase it, speak it instead.**

## Set up Wispr Flow

Voice-to-text tools work system-wide — they sit between your microphone and any text field. We'll use Wispr Flow here because it's what the author uses, but this isn't an endorsement — pick whatever works for you. Alternatives include Superwhisper *(Mac-only, privacy-focused)* and your OS's built-in dictation *(free but less accurate)*. The principles in this lesson apply to any of them.

Wispr Flow is fast, supports 100+ languages including Hinglish, and works across Mac, Windows, iOS, and Android.

Download Wispr Flow from [wisprflow.ai](https://wisprflow.ai/). All new accounts get a 14-day free trial of the Pro plan — no credit card required.

Once installed:

1. Open any text field — a chat window, a prompt box, a document
2. Press the dictation hotkey (configurable in settings)
3. Speak naturally
4. Text appears when you stop or press the hotkey again

### Things worth knowing

- **Hinglish works.** If you naturally mix Hindi and English, Wispr Flow has a dedicated model for that — no need to pick one language.
- **Whispering works.** You don't need to project — speaking quietly at your desk is fine. Useful in shared spaces or late at night.
- **Response time is fast.** Transcription appears almost instantly, not after a noticeable delay.
- **Autocorrect can backfire.** Wispr Flow applies autocorrection by default, which sometimes "fixes" variable names, jargon, or unusual phrasing into something wrong. **This works well when you speak clearly and use natural language** — but trips on dense technical dictation. Add frequently-used terms to the custom dictionary to teach it your vocabulary.
- **Regional pricing available.** In India, plans start around INR 400/month as of early 2026. Prices display in your local currency — check [wisprflow.ai/pricing](https://wisprflow.ai/pricing) for current plans.
- **The free tier gives you 2,000 words/week on desktop** and 1,000 on mobile — enough to test whether voice dictation fits your workflow before paying.

## Verify

**Test 1 — natural language prompt:** Open your AI agent's prompt input (Claude Code, Cursor, ChatGPT, whatever you use). Press the Wispr Flow hotkey and speak: "Create a Python function that takes a list of numbers and returns the three largest." Check that the text appeared accurately and the agent understood it.

**Test 2 — feel the limits:** Now try dictating something precise: a file path, a variable name, or a sentence with a technical term your agent needs to get exactly right. Notice where the transcription drifts. **This is the boundary — voice for natural language, keyboard for exact syntax.**

## Common failure modes

**The hotkey conflicts with another app.** If pressing the hotkey doesn't activate dictation, another app may have claimed that shortcut. Remap it in Wispr Flow's settings.

**Background noise tanks accuracy.** Voice-to-text works best in reasonably quiet environments. If accuracy drops suddenly, check your environment before blaming the tool.

## What you need

A computer or phone with a microphone (built-in is fine). The Wispr Flow free tier is enough to complete this lab.
