# Slide 4 — The Daily Workflow: When to Use a Single Prompt vs an Agent Loop (Flowchart)

**Purpose:** give a repeatable decision process that prevents wasted time

## The three modes (teach these explicitly)
### 1) Single prompt mode (fast Q&A)
- Explanation, small snippet, clarify API usage, one-file helper
- You are still the integrator.

### 2) Agent loop mode (multi-step)
- Multi-file change, refactor + tests, structured bugfix with reproduction
- Requires a plan + evidence gates.

### 3) Human-first mode
- Architecture decisions, unclear requirements, safety-critical logic changes, ambiguous bugs without reproduction

## Flowchart (talk track)
1) Do we understand the task?
- If not: spend 5 minutes to define:
  - smallest deliverable
  - constraints
  - acceptance check

2) Is this high risk?
- If yes: add gates:
  - plan → diff → tests → review checklist

3) Do we have an oracle (tests / simulator / golden files / corpus)?
- If no: first task is “create the oracle” (baseline tests/logs)

4) Choose mode and proceed:
- Single prompt vs agent loop vs human-first

5) Always end with “prove it”
- test output, diff summary, benchmark, trace, regression report

## Suggested visual
- **Big flowchart** with three exits: Single Prompt / Agent Loop / Human-first
- Small legend: “Plan → Act → Prove → Commit”

## Instructor notes
- Stress: “Agentic coding is not fewer steps; it’s *different steps*.”
- Make “prove it” a non-negotiable habit.

---

Previous: [Slide 3](03-context-engineering.md) | [Back to index](../index.md) | Next: [Slide 5](05-failure-patterns.md)

## References
- [Get started with GitHub Copilot in VS Code](https://code.visualstudio.com/docs/copilot/getting-started) — A practical baseline for when to use inline suggestions vs agent mode, and how to review/accept changes as part of a daily workflow.
- [Security (VS Code Copilot)](https://code.visualstudio.com/docs/copilot/security) — Explains risk points in agentic flows (terminal execution, tool approvals, prompt injection) and the “trust boundaries” that justify adding explicit gates.
- [Building effective agents (Anthropic)](https://www.anthropic.com/research/building-effective-agents) — Provides the clearest framing for choosing simpler workflows vs full agent loops, and stresses checkpoints, ground-truth tool feedback, and stop conditions.
- [Continuous integration (GitHub Actions)](https://docs.github.com/en/actions/automating-builds-and-tests/about-continuous-integration) — Anchors the “prove it” step by describing CI as repeatable build/test automation that catches regressions early.
- [About GitHub Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent) — Useful for explaining the PR-centric agent workflow on GitHub (background execution, review checkpoints, and built-in guardrails) as a complement to IDE agent loops.
