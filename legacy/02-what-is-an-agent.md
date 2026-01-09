# Slide 2 — What an Agent Is (and Isn’t): The “Eager Junior with Superpowers”

**Purpose:** make capabilities + limits tangible; normalize failures

## Definition (plain language)
- An “agent” is an AI-assisted workflow that can:
  - reason about a goal,
  - plan steps,
  - take actions (read code, propose edits, run tools),
  - iterate until the goal is met (or it gets stuck).

> Mental model: an always-eager junior teammate who reads fast and types fast, but needs supervision and a test oracle.

## What Copilot-style agents can do well (examples across domains)
- **Embedded / firmware:** “Trace state-machine logic, add guard conditions, generate simulator tests” *(with strong constraints!)*
- **Industrial / controls / robotics:** “Audit safety interlocks, add unit/tolerance checks, update control-loop tests in simulation/HIL”
- **DevOps / SRE:** “Triage an incident from logs/metrics, draft a runbook update, propose a safe rollout + rollback plan”
- **Cybersecurity / AppSec:** “Triage a vuln report, propose a minimal fix, add a regression test, and verify no secrets leak”
- **Data / ML:** “Validate dataset schema, add pipeline checks, run an eval notebook-to-script, and report drift/regression”
- **Scientific / HPC / simulation:** “Refactor a numerical kernel, add golden-output regression tests, and run perf benchmarks”

## Where agents fail (common failure modes)
- Confidently wrong / plausible nonsense
- Missing hidden constraints (legacy quirks, performance, real-time, encoding)
- Over-generalizing “best practices” into the wrong environment
- Thrashing: tries multiple random changes without a stable hypothesis
- Tool misuse: wrong commands, wrong environment assumptions, partial runs

## Suggested visual
- **2×2 chart:** Ambiguity (low→high) vs Risk (low→high)
  - Low ambiguity + low risk: great for agents (docs, refactors, formatting, small test additions)
  - High ambiguity or high risk: requires stronger specs + human gates

## Instructor notes
- Make it safe to admit: “If you tried once and it wasted time, that’s a predictable failure mode—today we’ll fix the *process*.”

---

Previous: [Slide 1](01-2025-shift.md) | [Back to index](../index.md) | Next: [Slide 3](03-context-engineering.md)

## References
- [Building effective agents](https://www.anthropic.com/research/building-effective-agents) — Defines “workflows vs agents” and explains why agent loops need checkpoints, tool feedback, and clear stop conditions.
- [About GitHub Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent) — Makes the “eager junior teammate” model concrete by documenting capabilities, limitations, and built-in governance/security.
- [GitHub Copilot in VS Code](https://code.visualstudio.com/docs/copilot/overview) — Shows what “autonomous coding” means in practice (multi-step work, tool/terminal usage, iteration) so people know what to expect.
- [What is Foundry Agent Service?](https://learn.microsoft.com/en-us/azure/ai-foundry/agents/overview) — A clean agent definition (model + instructions + tools) plus enterprise concepts (observability/trust) that map well to risk gating.
- [LLM01:2025 Prompt Injection](https://genai.owasp.org/llmrisk/llm01-prompt-injection/) — Explains why tool-using agents increase attack surface and why “least privilege + human approval” matters.