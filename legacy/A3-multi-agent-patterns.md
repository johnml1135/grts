# Appendix A3 — Multi-Agent & Async Patterns (Optional)

**Use:** show “what’s next” without overwhelming

## When multi-agent helps
- Parallel research: API docs, legacy behavior, bug history, test flakiness
- Separation of concerns:
  - Planner agent: decomposes tasks and risks
  - Implementer agent: makes changes + tests
  - Reviewer agent: checks constraints + style + safety

## Practical tip
- Use separate working directories (e.g., git worktrees) for parallel experiments
- Use long-running/async tasks for big test matrices or doc generation

## Suggested visual
- 3-lane swim diagram: Planner → Implementer → Reviewer with artifacts passed between lanes

---

Previous: [Appendix A2](A2-rules-of-engagement.md) | [Back to index](../index.md) | Next: [Speaker Prep](speaker-prep.md)

## References
- [Building effective agents (Anthropic)](https://www.anthropic.com/research/building-effective-agents) — Provides concrete multi-agent/workflow patterns (parallelization, orchestrator-workers, evaluator-optimizer) and when they’re worth the complexity.
- [Tutorial: Work with agents in VS Code](https://code.visualstudio.com/docs/copilot/agents/agents-tutorial) — Covers background agents and how they isolate work in Git worktrees, which is a practical way to run parallel “roles.”
- [git-worktree documentation](https://git-scm.com/docs/git-worktree) — The underlying Git mechanism for multiple working directories from one repo, supporting parallel experiments and quick context switching.
- [About GitHub Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent) — A real-world async agent pattern (PR-based, runs in an ephemeral environment) that mirrors “delegate + review” at team scale.
