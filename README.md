# Sensei

A curriculum for teaching agentic AI — written by AI, taught to humans, delivered through Discord.

Sensei is a structured learning system where Claude Code acts as the instructor. It produces lessons, maintains tracks, and posts content to Discord forums. The human role is to point it at topics and review the output.

## Tracks

The curriculum follows the Agentic Maturity Ladder — seven levels of operating sophistication with coding agents:

| Level | Name | What it looks like |
|-------|------|--------------------|
| 1 | **Vibing** | Using a coding agent naturally, judging results by feel |
| 2 | **Operating** | The setup around the agent carries more of the work for you |
| 3 | **Directing** | You define success, constraints, and verification before work starts |
| 4 | **Delegating** | You assign bounded tasks to agents and review outputs |
| 5 | **Orchestrating** | You run a coordinated team of agents with stable roles |
| 6 | **Systemizing** | You build reusable harnesses, workflows, and guardrails |
| 7 | **Compounding** | Prior work becomes trusted leverage that improves future work |

### Vibe Coding
Covers **Levels 1–2** (Vibing → Operating). How to use AI coding agents effectively — setup, tools, MCP, automation, and real projects. For developers moving from chat to agents.

### Agentic Engineering
Covers **Levels 3–5** (Directing → Orchestrating). How to give clear briefs, delegate bounded work, and run coordinated agent teams. For engineers ready to build beyond the defaults.

### Compounding Engineering
Covers **Levels 6–7** (Systemizing → Compounding). How to encode good practice into reusable infrastructure and make prior work improve future work automatically.

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
