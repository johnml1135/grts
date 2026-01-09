# Slide 3 — The Core Skill: Context Engineering (Orientation • Tools • Objectives)

**Purpose:** explain why prior attempts failed; teach the “investment” mindset

## Big idea
- Since Fall 2025 (GPT 5.2, Gemini 3, Opus 4.5), agents are not often limited by intelligence.
- Most agent failures are **context failures**, not “model intelligence” failures.
- Your competitive advantage becomes: **making intent + constraints + verification explicit**.

## The Context Engineering Triangle
### 1) Orientation (how we work here)
- Repo conventions, style rules, naming, folder structure
- How to build/test/lint
- What “done” looks like (PR expectations)
- Domain rules:
  - units/tolerances (industrial controls / robotics)
  - timing/memory (embedded / firmware)
  - blast radius + rollout/rollback expectations (DevOps / SRE)
  - threat model + secrets handling rules (security / AppSec)
  - data lineage, privacy, reproducibility constraints (data / ML)
  - numerical stability + determinism expectations (simulation / HPC)
  - safety/compliance constraints

#### Concrete orientation assets (make “how we work” explicit)

- **Repo instructions**
  - This repo uses `copilot-instructions.md` as a teaching aid; in production you typically use `.github/copilot-instructions.md`.
  - You can also add **path-specific / per-job instructions** via `.github/instructions/*.instructions.md` (e.g., backend vs frontend, data vs infra).
- **Copilot Chat custom agents**
  - Create named agents with a clear role (e.g., “Test Writer”, “Refactorer”, “Doc Editor”) and explicit boundaries so the model stops role-switching mid-task.

### 2) Tools (what Copilot can use / what *you* will run)
- IDE + terminal workflow
- Test runner, linter, formatter, benchmarks
- Search tools (repo search, docs)
- Git/GitHub as **truth sources**: diffs, CI checks, PR reviews

#### Concrete tool examples (make “what’s true” accessible)

- **Context7 (MCP: up-to-date library docs)**
  - Add: a `.vscode/mcp.json` entry (workspace) or your client’s global MCP config.
  - Docs: https://github.com/upstash/context7
  - Blog: https://upstash.com/blog/context7-mcp
  - Guidance: Use when touching third-party libraries/frameworks; treat it as **API truth** to reduce stale examples and hallucinated usage.

- **Serena (MCP: semantic code retrieval + symbol-level edits)**
  - Add: a `.vscode/mcp.json` entry; optionally `.serena/project.yml` if you adopt Serena’s project workflow.
  - Docs: https://oraios.github.io/serena/02-usage/030_clients.html
  - Blog: https://robertmarshall.dev/blog/turning-claude-code-into-a-development-powerhouse/
  - Guidance: Use on medium/large repos to find and edit by *intent* (symbols + references) instead of grepping and whole-file rewrites. On Windows, watch JSON escaping for paths.

### 3) Objectives (what success means)
- A small spec: behavior + constraints + non-goals
- An oracle: tests, golden files, simulation runs, expected outputs
- Stop conditions: when to ask a human, when to stop iterating

#### Concrete objective artifacts (make “done” legible)

- **OpenSpec / Spec-driven docs** (a written spec that survives the chat window)
- **Spec Kit**: Spec → Plan → Tasks as explicit phase gates
- **Jira issues** (or equivalent): scope, acceptance criteria, constraints
- **Markdown files in-repo**: specs/ADRs/runbooks/checklists that become durable context assets

## “Why this matters” story (1 minute)
- Without Objectives: agent ships plausible code that doesn’t meet real constraints.
- Without Tools: agent can’t prove anything.
- Without Orientation: agent fights your codebase and makes it worse.

## Suggested visual
- Triangle diagram labeled Orientation / Tools / Objectives
- Around the edges: 1–2 concrete examples per domain

## Instructor notes (Copilot-specific)
- Encourage a “project briefing” habit:
  - “Here’s how to run tests”
  - “Here are constraints”
  - “Here is the acceptance check”
- Emphasize: context is not a one-time prompt; it’s **assets** you maintain.

---

Previous: [Slide 2](02-what-is-an-agent.md) | [Back to index](../index.md) | Next: [Slide 4](04-daily-workflow.md)

## References
- [Adding repository custom instructions for GitHub Copilot](https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions) — Shows how to make “orientation” persistent via repo instruction files so the agent stops guessing your conventions.
- [Tutorial: Work with agents in VS Code](https://code.visualstudio.com/docs/copilot/agents/agents-tutorial) — Covers agent workflows and is a good anchor for adopting (and operationalizing) Copilot Chat custom agents.
- [Context7 (GitHub)](https://github.com/upstash/context7) — Provides up-to-date library documentation via MCP so you can treat third‑party APIs as “truth” instead of guessing.
- [Serena docs](https://oraios.github.io/serena/02-usage/030_clients.html) — Shows how to use semantic retrieval and symbol-level edits to refactor/search by intent instead of grepping and rewriting whole files.
- [Spec Kit](https://github.github.io/spec-kit/) — A concrete Spec → Plan → Tasks workflow that turns vague objectives into explicit deliverables, gates, and stop conditions.
