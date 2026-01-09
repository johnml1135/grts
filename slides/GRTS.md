---
marp: true
paginate: true
header: '<img src="../GRTS.png" class="logo" />'
footer: 'Guidance | Reality Rules Roles | Tools | Specifications'
style: |
  section {
    padding-top: 50px;
    padding-bottom: 50px;
    display: flex !important;
    flex-direction: column !important;
    justify-content: flex-start !important;
    align-items: stretch !important;
  }

  section > h1:first-child,
  section > h2:first-child,
  section > h3:first-child {
    margin-top: 0;
  }

  header {
    position: absolute;
    top: 16px;
    right: 16px;
    left: auto;
    margin: 0;
    width: auto;
  }

  header img.logo {
    height: 144px;
  }

  footer {
    position: absolute;
    bottom: 16px;
    left: 0;
    width: 100%;
    margin: 0;
    text-align: center;
    font-style: italic;
    font-size: 0.95em;
    letter-spacing: 0.02em;
    opacity: 0.85;
  }

  .anchor {
    text-align: center;
    font-style: italic;
    font-size: 0.95em;
    letter-spacing: 0.02em;
    opacity: 0.85;
    margin: 0 0 10px 0;
  }

  .title-logo {
    display: block;
    margin: 70px auto 18px auto;
    width: 360px;
  }

  .centered {
    text-align: center;
  }

  .subline {
    font-size: 0.7em;
    opacity: 0.85;
    font-weight: 400;
    margin-left: 0.5em;
    white-space: nowrap;
  }

  .g { color: #80b040; }
  .r { color: #e02020; }
  .t { color: #d0a030; }
  .s { color: #1090c0; }
---

<!--
Marp slide deck notes:
- Global logo is in the header (top-right) on every slide.
- Use the centered “anchor” line to visually align the deck.
-->

<!-- _footer: "" -->
<!-- _header: "" -->

<div class="anchor">Guidance 🧭 | Reality Rules Roles 🧱 | Tools 🧰 | Specifications ✅</div>

<img class="title-logo" src="../GRTS.png" />


<div class="centered">Don’t build features. <b>Build the system that builds features.</b></div>

---
<!-- fit --->
# Coding Agent 🍺🤖 The very eager stupid genius
<style scoped>
p { text-align: center; }
</style>
![height:500px](assets/grts-slide2-flowchart.svg)

<!-- _notes:
Purpose: Reset expectations; reduce hype; validate skepticism.
Emphasize: "Don’t build features. Build the system that builds features."
-->

---
# <span class="g">🧭 Guidance</span> <span class="subline">Prompting | Supervision | Hand-holding</span>
<style scoped>
section {
    font-size: 24px;
}
</style>
* Rabbit hole:
  * Is this the best approach?
  * Research best practices (≥5 sources).
  * Give the best 3 approaches with pros/cons — cite evidence.
* Shortcut:
  * What are the best practices here?
  * **NEVER IGNORE TESTS OR COMMENT THEM OUT**
  * Right place for the code? Clean architecture? Utilities library?
* Define “good”:
  * **Verification vs Validation** — built the thing right vs build the right thing &larr; we need this!
  * Use an oracle / golden sample / explicit success criteria.
---
# <span class="r">🧱 Reality | Rules | Roles</span> <span class="subline">Instructions | Skills | Orientation | Foundation</span>
<style scoped>
section {
    font-size: 24px;
}
</style>
* Build repo overview + working rules (copilot-instructions.md) &larr; **Copilot can help with this!**
* Cite docs: build scripts, library locations, standards, linting guides
* For the top 3–8 areas, define “roles” with repo-specific best practices (xyz.instructions.md / Claude skills)
* Define boundaries: excluded (secrets), auto-approved (git fetch/status), and restricted files (CI/CD, security)
## Tips:
* Keep instruction files short (100–300 lines). Refine or split as needed.
* Spend 1–2 days iterating; this pays off.
* When prompts miss something (edge cases, wrong file, global var), explain the failure and update the right instruction file.
---
# <span class="t">🧰 Tools</span> <span class="subline">Capabilities | Abilities | Touch the external world</span>

Without extra tools, agents are limited to reading and writing files in your repo.

* Issue read and write: [GitHub MCP](https://github.com/github/github-mcp-server) [Atlassian MCP](https://www.atlassian.com/blog/announcements/remote-mcp-server)
* Accurate API and function calls: Context7 + research online
* Deterministic actions: generate a script for repetitive/complex work (e.g., convert NUnit3 tasks to NUnit4 across many files)
* VS Code tasks: Build, test, lint, format, etc.
* Shell commands: git status, list files, get file content
* Tip: Use settings.json -&gt;"chat.tools.terminal.autoApprove" for read-only commands

---
# <span class="s">✅ Specifications</span> <span class="subline">Objectives | Checklists | Planning | Requirements</span>

* You mostly review outputs and spot-check code/decisions.
* For larger work, spend time planning to reduce churn and wrong turns.
* **Level 1**: For bugs and scoped changes, we can just make a single prompt
* **Level 2**: 1–3 planning prompts (research/explain/3 options) → then implement
* **Level 3**: Create a checklist in Markdown → review → implement
* **Level 4**: Use [OpenSpec](https://github.com/Fission-AI/OpenSpec) or [Spec-Kit](https://github.com/github/spec-kit): specify → clarify → plan → analyze → implement

---
# A1: Multi-agent workflows

* You’ll often be waiting on agents. Use that time:
  * Research the next feature in parallel
  * Use git worktrees (VS Code + Agent HQ) for parallel branches
  * Delegate to cloud agents (ensure CI/CD is set up)


Reference: [Agent HQ](https://visualstudiomagazine.com/articles/2025/12/12/vs-code-1-107-november-2025-update-expands-multi-agent-orchestration-model-management.aspx) — Background on VS Code’s emerging multi-agent orchestration model and how it changes day-to-day workflow. Useful context for why parallel work (e.g., via git worktrees) matters.

---
# A2: Risk -> Gating | Ambiguity -> Planning
<style scoped>
section {
    font-size: 22px;
}

table {
  margin-left: auto;
  margin-right: auto;
  border-collapse: collapse;
  border: 3px solid currentColor;
}

th,
td {
  text-align: center;
  border: 2px solid currentColor;
  padding: 0.35em 0.6em;
}

th {
  border-bottom-width: 3px;
}

td ul {
  list-style: none;
  padding-left: 0;
  margin: 0;
}

td li {
  margin: 0;
  padding: 0;
}
</style>
| The good | The bad and the ugly |
|---|---|
| <ul><li>reason about the goal</li><li>plan steps</li><li>take actions (read/edit/run tools)</li><li>iterate until done (or stuck)</li></ul> | <ul><li>confidently wrong</li><li>misses hidden constraints</li><li>misapplies “best practices”</li><li>thrashes without a stable hypothesis</li><li>misuses tools (wrong env/partial runs)</li></ul> |

| | **Risk: Low** | **Risk: High** |
|---|---|---|
| **Ambiguity: Low** | Great for agents (docs, refactors, small tests) | Needs gates + review (small but critical changes) |
| **Ambiguity: High** | Clarify first (spec + oracle) | Human-first (architecture/safety-critical/unclear bugs) |

---
<!-- fit -->
# A3: Main References
<style scoped>
section {
    font-size: 22px;
}
</style>
- **G** — [Lessons from Anthropic](https://techwithibrahim.medium.com/the-art-of-agent-prompting-lessons-from-anthropics-ai-team-e8c9ac4db3f3) — A practical set of prompting lessons for giving better guidance.
- **G** — [Lessons from Anthropic](https://techwithibrahim.medium.com/the-art-of-agent-prompting-lessons-from-anthropics-ai-team-e8c9ac4db3f3) — Prompting lessons for better guidance.
- **G** — [Building effective agents (Anthropic)](https://www.anthropic.com/research/building-effective-agents) — Designing agent loops: checkpoints, tool feedback, stop conditions.
- **R** — [Security (VS Code Copilot)](https://code.visualstudio.com/docs/copilot/security) — Risk areas and guardrails.
- **R** — [Workspace Trust (VS Code)](https://code.visualstudio.com/docs/editing/workspaces/workspace-trust) — Trust boundaries + Restricted Mode.
- **R** — [LLM01:2025 Prompt Injection](https://genai.owasp.org/llmrisk/llm01-prompt-injection/) — Prompt injection risks + mitigations.
- **T** — [Tutorial: Work with agents in VS Code](https://code.visualstudio.com/docs/copilot/agents/agents-tutorial) — Running agent workflows in the IDE.
- **S** — [Spec Kit](https://github.github.io/spec-kit/) — Spec → Plan → Tasks to make “done” measurable.
- **S** — [CI (GitHub Actions)](https://docs.github.com/en/actions/automating-builds-and-tests/about-continuous-integration) — CI as a repeatable verification oracle.
- **S** — [A Minimal, Reproducible Example](https://stackoverflow.com/help/minimal-reproducible-example) — Make bugs/tasks reproducible.
- **S** — [Responsible use of GitHub Copilot coding agent](https://docs.github.com/en/copilot/responsible-use-of-github-copilot-features/responsible-use-of-copilot-coding-agent-on-githubcom) — Scope, acceptance criteria, review gates.

---
<!-- fit -->
# A4: Auxiliary References
<style scoped>
section {
    font-size: 22px;
}
</style>

- [GitHub Copilot Workspace: Welcome to the Copilot-native developer environment](https://github.blog/2024-04-29-github-copilot-workspace/)
- [GitHub Copilot in VS Code](https://code.visualstudio.com/docs/copilot/overview)
- [Asking GitHub Copilot questions in your IDE](https://docs.github.com/en/copilot/how-tos/chat-with-copilot/chat-in-ide)
- [Get started with GitHub Copilot in VS Code](https://code.visualstudio.com/docs/copilot/getting-started)
- [Use tools in chat (VS Code) — Tool approval](https://code.visualstudio.com/docs/copilot/chat/chat-tools)
- [Review AI-generated code edits (VS Code)](https://code.visualstudio.com/docs/copilot/chat/review-code-edits)
- [Adding repository custom instructions for GitHub Copilot](https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions)
- [About GitHub Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent)
- [What is Foundry Agent Service?](https://learn.microsoft.com/en-us/azure/ai-foundry/agents/overview)
- [Context7 (GitHub)](https://github.com/upstash/context7)
- [Serena docs](https://oraios.github.io/serena/02-usage/030_clients.html)
- [git-worktree documentation](https://git-scm.com/docs/git-worktree)
- [About issue and pull request templates (GitHub)](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/about-issue-and-pull-request-templates)
- [Configuring issue templates for your repository (GitHub)](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository)