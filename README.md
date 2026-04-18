# Sensei

A curriculum for teaching agentic AI — written by AI, taught to humans, delivered through Discord.

Sensei is a structured learning system where Claude Code acts as the instructor. It produces lessons, maintains tracks, and posts content to Discord forums. The human role is to point it at topics and review the output.

## Tracks

The curriculum follows the Agentic Engineering Ladder — eight levels of operating sophistication with coding agents:

| Level | Name | What you'll learn |
|-------|------|-------------------|
| 1 | **Vibing** | Use a coding agent for real work just by asking naturally — no special setup or expertise required |
| 2 | **Operating** | Set up tools and environments that make your agent dramatically more capable — so you get better results without thinking harder |
| 3 | **Directing** | Write briefs that get consistent, verifiable results — so you stop getting outputs that look right but aren't |
| 4 | **Delegating** | Split complex work across multiple agents — so you can tackle bigger projects than any single agent can handle cleanly |
| 5 | **Orchestrating** | Run a team of agents with defined roles and real handoffs — so complex, multi-part work gets done without you being the bottleneck |
| 6 | **Systemizing** | Build workflows that combine deterministic steps with AI — so you reduce the uncertainty in agent behavior and dramatically improve accuracy and reliability |
| 7 | **Compounding** | Structure memory and context so past work carries forward — so every task you do makes the next one better |
| 8 | **Evolving** | Build a feedback loop that improves your whole system over time — so it keeps getting better even when you're not actively working on it |

## Lesson Format

Every lesson is a markdown file with:

- **YAML frontmatter** — title, track, order, prerequisites, tags
- **Overview** — what and why, in two sentences
- **Concept** — the idea explained, with tables or diagrams where useful
- **How-To** — real commands, configs, or code
- **Decision Framework** — when to use this vs. alternatives
- **Failure Modes** — what goes wrong and how to recover
- **Try This Now** — one concrete exercise
- **Key Takeaway** — the one thing to remember

Target length: 600–900 words. Practical over theoretical. No filler.

## How Lessons Get Made

Claude Code ingests source material (videos, articles, transcripts) into the wiki, then generates lessons from synthesized knowledge. Lessons are reviewed by the human, then posted to Discord forums via the `discord` skill.

To add a lesson:
1. Drop source material in `raw/` or provide a URL
2. Run `/ingest` to process it into the wiki
3. Ask Claude to draft a lesson for the relevant track
4. Review and approve
5. Claude posts it to the Discord forum

## Discord

Lessons are published to **The New Order** Discord server — one lesson per forum post, organized by track. Each post is self-contained: a learner should be able to read it cold and walk away with something actionable.
