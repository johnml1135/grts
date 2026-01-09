# Appendix A2 — Team “Rules of Engagement” Checklist (1 page)

**Use:** reduce risk + increase repeatability

## Agent may do
- propose a plan
- make changes in scoped directories
- add or modify tests
- write docs / comments
- run local commands (with your approval) or suggest commands to run

## Agent may NOT do (without explicit permission)
- change build pipelines, security settings, or dependencies
- refactor cross-cutting architecture
- modify safety-critical logic without extra review
- commit secrets or sample real customer data

## Evidence required before merge
- tests green (list which)
- lint/format passes
- benchmarks / simulator outputs (if relevant)
- “what changed” summary + risks/assumptions

## Escalation rule
- If 3 iterations fail: stop, summarize findings, ask a human for a new hypothesis

---

Previous: [Appendix A1](A1-task-spec-template.md) | [Back to index](../index.md) | Next: [Appendix A3](A3-multi-agent-patterns.md)

## References
- [Security (VS Code)](https://code.visualstudio.com/docs/copilot/security) — Summarizes agent risk areas (execution, tool approvals, info exposure, prompt injection) and the corresponding mitigations (trust boundaries, controlled scope, review).
- [Workspace Trust (VS Code)](https://code.visualstudio.com/docs/editing/workspaces/workspace-trust) — Explains Restricted Mode and why agents are disabled in untrusted workspaces, reinforcing “don’t run what you don’t trust.”
- [Use tools in chat (VS Code) — Tool approval](https://code.visualstudio.com/docs/copilot/chat/chat-tools) — Details approval gates and auto-approval tradeoffs for tools and terminal commands, mapping directly to “may/may not” rules.
- [LLM01:2025 Prompt Injection (OWASP GenAI Top 10)](https://genai.owasp.org/llmrisk/llm01-prompt-injection/) — A canonical threat model for prompt injection plus mitigations like least privilege and human approval for high-risk actions.
- [About GitHub Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent) — Documents built-in guardrails (branch restrictions, workflow approval, sandboxing) that you can align your team’s governance checklist with.
