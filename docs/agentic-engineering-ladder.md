# The Agentic Engineering Ladder

Date: 2026-04-11

## At A Glance

> Placement rule: place someone at the highest level that matches their **default repeated behavior** on real work.

**Progression:** `Vibing` → `Operating` → `Directing` → `Delegating` → `Orchestrating` → `Systemizing` → `Compounding` → `Evolving`

| Level                | Mode                | What it looks like                                                                                          | Boundary to next level                                                               |
| -------------------- | ------------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **1. Vibing**        | Natural use         | You use a coding agent naturally and judge the result mostly by feel.                                       | You start using stronger tools, superpowers, and connected systems around the agent. |
| **2. Operating**     | Codified help       | You still talk naturally, but the setup around the agent makes the whole process much more capable for you. | You define outcomes, constraints, and verification explicitly.                       |
| **3. Directing**     | Clear briefs        | You define success, failure, tests, and acceptance criteria.                                                | You split work into bounded pieces with ownership and handoffs.                      |
| **4. Delegating**    | Sub-agent use       | You assign bounded tasks to agents and review their outputs.                                                | You coordinate multiple agents as one working system.                                |
| **5. Orchestrating** | Multi-agent flow    | You run a team of agents with roles, sequencing, and synthesis.                                             | You turn that workflow into reusable infrastructure.                                 |
| **6. Systemizing**   | Workflow design     | You build harnesses, rules, nodes, evals, and guardrails.                                                   | The system starts improving from prior work and memory.                              |
| **7. Compounding**   | Persistent leverage | Context, decisions, and patterns carry forward and increase future output.                                  | The system starts improving the compounding system itself.                           |
| **8. Evolving**      | Meta improvement    | The system observes, evaluates, and improves its own workflows, memory, agents, and harnesses over time.   | Highest level in this model.                                                         |

**In one line:** from using a coding agent naturally, to relying on stronger tools and codified system help, to directing it clearly, to delegating and orchestrating work, to building systems that compound, and eventually systems that improve themselves.

## Goal

Define a simple, publishable ladder for how people work with coding agents and AI systems.

This is not a ladder of:

- job title
- engineering seniority
- organizational scope
- model quality
- number of tools

It is a ladder of **agentic operating maturity**.

In plain terms:

> How sophisticated is your way of working with agents?

Baseline assumption:

- this ladder starts from using a real coding agent
- examples include tools like Claude Code, Codex, Cursor agents, or similar agentic coding systems
- `Vibing` does **not** mean chatting with a raw LLM in a blank text box
- even at the first level, you are already working through an agentic environment

The progression runs from natural use, to tool- and system-guided use, to explicit direction, to delegation, to orchestration, to reusable systems, to compounding leverage, and finally to systems that improve themselves.

## Scope And Tradeoffs

This model is for repeated coding-agent and knowledge-work settings.

It is most useful when:

- work spans multiple tasks or sessions
- verification matters
- context management matters
- delegation or coordination costs are real
- reuse can create leverage over time

Higher levels are not automatically better for every task.

For a one-off request, a clear bug, or a small local change, `Vibing`, `Operating`, or `Directing` may be the right level. The higher levels pay off when the cost of coordination, repeatability, and reuse justifies the extra structure.

## Placement Rule

Place someone at the **highest level that reflects their default mode on repeated work**.

To count as operating at a level, four things should be true:

- they do it intentionally, not accidentally
- they can repeat it across tasks, not just one impressive demo
- they can explain where the leverage is coming from
- they pass the boundary test for that level

If a person occasionally works at a higher level but cannot do so consistently, place them at the lower one.

If in doubt, level down. This model is meant to classify steady practice, not someone's best day.

## The Ladder

### 1. Vibing

You are using a proper coding agent, but mostly in the most natural and unstructured way possible.

Observable evidence:

- normal human-language requests
- minimal explicit steering beyond the request itself
- little or no explicit structure
- little or no discussion of constraints, tests, or verification
- output is judged mostly by whether it seems right

Typical behavior:

- "Build me this"
- "Fix this bug"
- "Make it look more modern"

Boundary test:

- if you cannot reliably state what success or verification should look like before the work starts, you are still here

Failure mode:

- confuses plausibility with correctness

### 2. Operating

You are still mostly talking to the coding agent naturally, but the setup around that agent is doing a lot more of the hidden work for you.

Observable evidence:

- tools, plugins, and superpowers around the agent
- connected environments such as editors, repos, or Obsidian workflows
- the agent can write files, surface context, and follow useful flows with much less effort from you
- the setup makes the process easier even if you do not understand all the underlying mechanics
- the main advantage comes from embedded structure and good defaults in the system

Typical behavior:

- you choose strong tools and agent environments
- you use things like Claude Code superpowers or connected tools that already codify useful practices
- you let the system handle more of the workflow for you
- for example, the agent writes files into a system like Obsidian and you work through that setup because it makes the process much easier
- you can get good results without fully understanding why a given workflow is right
- you still rely on the system to infer what done should mean

Boundary test:

- if your leverage comes mainly from tools, superpowers, and system design rather than from your own explicit framing, you are here

Failure mode:

- mistakes borrowed rigor for clear direction

### 3. Directing

You actively shape the work instead of just asking for it.

Observable evidence:

- clear task briefs
- explicit success criteria
- concrete constraints
- defined outputs
- specified verification steps
- clear test expectations

Typical behavior:

- you describe what success looks like
- you specify how the result should be verified
- you define tradeoffs, constraints, and boundaries up front

Boundary test:

- if the work still lives mostly in one thread or one agent, but the brief is precise and testable, you are here

Failure mode:

- writes long prompts without clear thinking

### 4. Delegating

You use agents as bounded workers, not just as one conversation partner.

Observable evidence:

- separate runs or sub-agents for distinct tasks
- explicit ownership of subtasks
- intentional handoffs
- separation between research, implementation, and review
- the human manually synthesizes outputs back together

Typical behavior:

- one agent explores
- one agent implements
- one agent verifies
- you split work to protect context and improve focus

Boundary test:

- if coordination still lives mostly in your head and is rebuilt manually each time, you are here and not yet `Orchestrating`

Failure mode:

- spawns extra agents without clear boundaries or ownership

### 5. Orchestrating

You are running a coherent team of agents, not just several separate ones.

Observable evidence:

- stable role definitions across tasks
- multiple agents working in parallel toward a shared outcome
- explicit dependency management between agents
- synthesis, arbitration, prioritization, and rerouting become part of the job
- there is a recognizable operating model, not just ad hoc delegation

Typical behavior:

- researcher, implementer, reviewer, verifier, and documenter agents have distinct jobs
- work is dispatched intentionally based on fit, not convenience
- you decide what stays local, what gets delegated, and how outputs rejoin the main flow

Boundary test:

- if your multi-agent process works only because you are manually recreating the same coordination pattern every time, you are not yet `Systemizing`

Failure mode:

- coordination overhead eats the gains

### 6. Systemizing

You build reusable infrastructure that makes good agentic work repeatable.

Observable evidence:

- reusable workflows
- harnesses
- domain-specific tools or nodes
- prompts and playbooks
- evals and checks
- review loops
- verification paths
- structured context-loading patterns

Typical behavior:

- good behavior becomes the default
- less depends on remembering the right thing in the moment
- your operating model is encoded into reusable process
- another person could adopt parts of your workflow without copying your whole brain

Boundary test:

- if the workflow is reusable but each new task still starts from near-zero memory, you are here and not yet `Compounding`

Failure mode:

- overengineers workflow sophistication without improving outcomes

### 7. Compounding

Your agentic system gets stronger over time because prior work becomes usable future leverage.

Observable evidence:

- prior work is reusable
- decisions are recoverable
- context persists across tasks in a structured way
- patterns, playbooks, prompts, and artifacts accumulate into leverage
- future tasks start ahead because the system can retrieve and apply past context

Typical behavior:

- memory is deliberate, not accidental
- lessons become reusable assets
- important context can be brought forward when needed
- the system develops continuity instead of resetting every time

Boundary test:

- if you are storing context but cannot reliably retrieve, trust, and apply it in future work, you are still at `Systemizing`

Failure mode:

- accumulates memory without curation and creates context sludge

### 8. Evolving

You build an outer loop that observes, evaluates, and improves the agentic system itself over time.

Observable evidence:

- evaluator loops for workflows, prompts, memory, tools, or agent roles
- explicit review of what parts of the system are working and what parts are drifting
- prompts, playbooks, harnesses, or agent structures get revised based on outcomes
- the system improves not just from stored history, but from deliberate self-improvement
- there is a meta-layer concerned with making the whole setup better over time

Typical behavior:

- you monitor how well the system is actually performing
- you refine or replace workflows when they stop being useful
- you improve memory quality, not just memory quantity
- you split, merge, or redesign roles as the system matures
- you build feedback loops that upgrade the way the compounding system works

Boundary test:

- if prior work helps future work, but there is no deliberate outer loop that improves the system itself, you are still at `Compounding`

Failure mode:

- builds recursive complexity with weak evaluation

## One-Line Summary

- `Vibing`: using a coding agent in the most natural way
- `Operating`: using tools and system help that codify the why for you
- `Directing`: defining success clearly
- `Delegating`: giving bounded work to agents
- `Orchestrating`: running a coordinated team of agents
- `Systemizing`: building reusable workflows and harnesses
- `Compounding`: making prior work improve future work
- `Evolving`: making the system improve itself over time

## The Hardest Boundaries

These are the distinctions skeptical readers will challenge first.

### Delegating vs Orchestrating

- `Delegating` means you can split work across agents well
- `Orchestrating` means you run a stable division of labor with explicit coordination logic

The difference is not "more agents." The difference is whether there is a real operating model.

### Orchestrating vs Systemizing

- `Orchestrating` is a human-managed craft
- `Systemizing` turns that craft into reusable infrastructure

The difference is not sophistication theater. The difference is whether the process can be rerun consistently.

### Systemizing vs Compounding

- `Systemizing` makes good behavior repeatable
- `Compounding` makes prior work improve future work

The difference is not merely storing memory. The difference is whether past work becomes trusted, retrievable leverage.

### Compounding vs Evolving

- `Compounding` means the system remembers and reuses
- `Evolving` means the system deliberately improves how that remembering and reuse work

The difference is not just having more history. The difference is whether there is an outer loop that makes the whole system better.

## Quick Assessment

Work through the questions in order. Each question is a gate. Stop at the first one where the answer is consistently no — your level is the one just before it. If all eight are yes, you are at Level 8.

1. When work starts, can you reliably state what success looks like and how you would verify it?
2. Do you actively choose tools, environments, and codified workflows that carry good defaults for you — even if you did not design them yourself?
3. Do you reliably define success criteria, constraints, and verification before the work starts — and does your work mostly live in a single thread or agent run?
4. Do you regularly split work across bounded agents or runs with clear ownership, even if you rebuild the coordination manually each time?
5. Do you run multiple agents with stable role definitions and explicit coordination logic — even if that coordination pattern has to be recreated manually for each project?
6. Is your multi-agent operating model encoded into reusable workflows, harnesses, or playbooks that someone else could run without being you?
7. Does prior work reliably improve future work through memory or artifacts you can retrieve, trust, and apply — not just store?
8. Is there a deliberate, ongoing outer loop that evaluates how well the system is working and actively improves the workflows, memory, prompts, roles, or harnesses themselves — not just occasionally patches them?

## How To Use This Ladder

Use it for:

- self-assessment
- coaching
- team language
- workflow design
- capability design

Do not use it as a proxy for:

- raw intelligence
- engineering seniority
- prestige
- title

Someone can be a senior engineer and still operate in `Vibing` or `Operating`.
Someone can be early-career and already operate in `Directing` or `Delegating`.

This ladder measures **how you work with agents**, not your whole professional value.

In practice, it works best when you assess:

- default behavior, not aspiration
- repeated work, not one-off demos
- operating discipline, not tooling glamour

## Anti-Patterns

### Mistaking tools for maturity

Having access to strong tools, superpowers, and codified workflows does not mean you are beyond `Operating`.

### Mistaking verbosity for direction

Long prompts are not the same thing as clear direction.

### Mistaking multiple agents for orchestration

If roles are fuzzy and handoffs are unclear, it is not really `Orchestrating`.

### Mistaking workflow complexity for system quality

If the harness is elaborate but outcomes do not improve, it is not really `Systemizing`.

### Mistaking stored context for compounding

If memory cannot be retrieved, reused, and trusted, it is not really `Compounding`.

### Mistaking complexity for evolution

If the system keeps adding meta-layers without improving outcomes, it is not really `Evolving`.

## Recommended Public Version

1. `Vibing`
2. `Operating`
3. `Directing`
4. `Delegating`
5. `Orchestrating`
6. `Systemizing`
7. `Compounding`
8. `Evolving`

Use this line with it:

> The ladder goes from using a coding agent naturally, to directing and coordinating agents more deliberately, to building systems where agentic work compounds, and finally to systems that improve themselves.

## Final Recommendation

Use this ladder as your default language when you want to describe maturity in agentic practice.

It is:

- simple
- directional
- intuitive
- broad enough for non-engineers and engineers
- explicit enough to classify people without collapsing everything into vibes

Most importantly, the names describe **modes of operating**. That makes the model easy to remember, easy to teach, and hard to confuse with seniority or tool choice.
