# Appendix A1 — Copy/Paste: Task Spec Template (1 page)

**Use:** turn vague work into agent-executable work

## Template
- **Problem statement (2–3 sentences):**
- **In scope:**
- **Out of scope / non-goals:**
- **Constraints:**
  - performance:
  - memory:
  - real-time / timing:
  - backward compatibility:
  - safety/security/compliance:
  - domain constraints (units/encoding/etc.):
- **Repo pointers (files / modules / links):**
- **Acceptance / definition of done:**
  - tests to add or run:
  - golden files / expected outputs:
  - benchmark thresholds:
- **Commands:**
  - build:
  - test:
  - lint/format:
- **Stop conditions / escalation:**
  - “If X happens, stop and ask a human.”

## Filled mini-example (legacy-ish)
- Problem: “Intermittent parse failure in log ingestion when encountering mixed encodings.”
- Constraints: “No new dependencies; must keep throughput within 5% of baseline.”
- DoD: “Add regression corpus; add unit test; prove perf; document behavior.”

---

Previous: [Slide 6](06-retraining-plan.md) | [Back to index](../index.md) | Next: [Appendix A2](A2-rules-of-engagement.md)

## References
- [Responsible use of GitHub Copilot coding agent on GitHub.com](https://docs.github.com/en/copilot/responsible-use-of-github-copilot-features/responsible-use-of-copilot-coding-agent-on-githubcom) — Provides concrete guidance on writing prompts/issues with a clear description, acceptance criteria, and file pointers (basically your template’s core).
- [About issue and pull request templates (GitHub)](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/about-issue-and-pull-request-templates) — Shows how teams standardize “what to include” so issues/PRs are consistently actionable for both humans and agents.
- [Configuring issue templates for your repository (GitHub)](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository) — Demonstrates turning that standardization into structured templates/forms that require the key fields needed to execute work without guesswork.
- [How to create a Minimal, Reproducible Example (Stack Overflow)](https://stackoverflow.com/help/minimal-reproducible-example) — A crisp checklist for making a task reproducible (inputs, steps, expected vs actual), which directly improves agent success on bugfix tickets.
