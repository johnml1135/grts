# Slide 6 — The Retraining Plan: 2 Weeks to Daily Productivity (Not Just Demos)

**Purpose:** make adoption concrete for mixed skill levels + domains

## Principle
- Start with low-risk tasks that have high feedback.
- Build trust by building oracles (tests, golden files, scripts) and using them every time.

## Week 1: mechanics + trust (low risk, high feedback)
- Day 1–2: AI for reading
  - summarize modules, find call sites, explain tests, map architecture
- Day 3–4: one-file improvements
  - refactors with tests, logging improvements, doc fixes, small utilities
- Day 5: build the oracle
  - add/extend tests, golden file diffs, baseline benchmarks, simulator scripts

## Week 2: controlled agent loops
- Scoped tickets: small bugfixes, small migrations, a single component refactor
- Required artifacts:
  - brief plan
  - evidence (test output / diffs / benchmarks)
  - a “risks & assumptions” note

## Role-based entry points (so everyone can start)
- Interns: docs + test additions + small refactors
- Test techs: failure triage scripts, log parsing, test case generation
- Embedded / firmware: simulation-based assertions, unit/tolerance checks, state-machine tests
- Industrial / controls / robotics: HIL/simulator checks, safety interlock tests, trace-based debugging
- DevOps / SRE: alert triage, runbook updates, safe rollout + rollback scripts, IaC changes with validation
- Cybersecurity / AppSec: vuln triage, minimal patches with regression tests, dependency audit follow-ups
- Data / ML: dataset schema checks, pipeline validations, eval harnesses, reproducibility improvements
- Scientific / HPC / simulation: golden-output regression tests, perf baselines, numerical correctness checks

## Suggested visual
- Adoption ladder: Read → Edit → Refactor → Test/Oracle → Agent loop → Multi-agent patterns

## Instructor notes
- Emphasize: “The goal is not to trust the agent. The goal is to trust your *verification*.”

---

Previous: [Slide 5](05-failure-patterns.md) | [Back to index](../index.md) | Next: [Appendix A1](A1-task-spec-template.md)

## References
- [Building effective agents (Anthropic)](https://www.anthropic.com/research/building-effective-agents) — Frames adoption as “add complexity only when it pays,” and emphasizes ground-truth feedback plus explicit stopping conditions, matching the “trust verification” message.
- [Tutorial: Work with agents in VS Code](https://code.visualstudio.com/docs/copilot/agents/agents-tutorial) — A practical walkthrough of moving from local agent work to plan/background agents and cloud agents, mapping cleanly to a staged retraining ladder.
- [Continuous integration (GitHub Actions)](https://docs.github.com/en/actions/automating-builds-and-tests/about-continuous-integration) — Explains CI as automated build/test feedback on every change, i.e., the “oracle” that makes agent-driven edits safe and measurable.
- [Responsible use of GitHub Copilot coding agent on GitHub.com](https://docs.github.com/en/copilot/responsible-use-of-github-copilot-features/responsible-use-of-copilot-coding-agent-on-githubcom) — Highlights well-scoped tasks, explicit acceptance criteria, and review/testing as the core levers for reliable agent outcomes.
