# Slide 5 — Stop Burning Time: 6 Failure Patterns (and the Fixes)

**Purpose:** directly address the “I tried it; it wasted time” group

## Pattern → Replacement habit
1) **Big vague request** → “One deliverable + one acceptance test”
2) **No local reproduction** → “Write a repro script or a failing test first”
3) **Agent thrashing** → “Require a plan; cap iterations; switch to diagnosis-only”
4) **Hidden constraints** → “Put constraints in a persistent place (team notes / repo docs)”
5) **Tool friction** → “Standardize commands; templates; copy-pasteable run steps”
6) **No review boundary** → “Define allowed files; require diffs; checklist before commit”

## Optional mini-script (instructor reads)
- “Before you write code, ask the agent: *What information do you need to avoid guessing?*”
- “After code is written, ask: *Show evidence: what tests ran, what changed, what risks remain.*”

## Suggested visual
- Two-column table: “Anti-pattern” vs “New habit”
- Small “time budget” bar: 10% plan, 60% agent work, 30% verification (example)

---

Previous: [Slide 4](04-daily-workflow.md) | [Back to index](../index.md) | Next: [Slide 6](06-retraining-plan.md)

## References
- [How to create a Minimal, Reproducible Example (Stack Overflow)](https://stackoverflow.com/help/minimal-reproducible-example) — A canonical guide for “make it reproducible” so debugging (human or agent) starts from a concrete failing case instead of vibes.
- [Building effective agents (Anthropic)](https://www.anthropic.com/research/building-effective-agents) — Reinforces “simplest thing first,” plus practical guardrails like checkpoints, ground-truth tool feedback, and explicit stopping conditions to prevent thrash.
- [Use tools in chat (VS Code) — Tool approval](https://code.visualstudio.com/docs/copilot/chat/chat-tools) — Documents approval gates (including URL post-approval to mitigate prompt injection) and terminal auto-approval tradeoffs, directly mapping to safe agent habits.
- [Review AI-generated code edits (VS Code)](https://code.visualstudio.com/docs/copilot/chat/review-code-edits) — Shows the built-in Keep/Undo review flow and how to require explicit approval for sensitive-file edits, which helps enforce a clear review boundary.
- [Adding repository custom instructions for GitHub Copilot](https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions) — Explains how to make constraints and “how we work here” persistent (repo-wide and path-specific) so they don’t get lost between sessions.
