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
    top: 24px;
    right: 24px;
    left: auto;
    margin: 0;
    width: auto;
  }

  header img.logo {
    height: 100px;
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
    margin: 70px auto 70px auto;
    width: 240px;
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

<!--
Talk track (why this deck exists):
- In 2024, AI helped you write lines.
- In 2025, AI can help you move work across the lifecycle: search → plan → edit → test → summarize.
- For regulated / legacy / nonstandard domains, this is often *more* valuable because it forces explicit constraints, repeatable checks, and documented decisions.

Set expectations:
- The model is not the bottleneck; context + verification is.
- We’re not here to vibe-code a website. We’re here to safely move work in weird repos.

Repeat the mantra once, then translate it:
- “System” = durable orientation + tools + objective oracles + gates.
-->

---
<!-- fit -->
# Coding Agent: The very eager stupid genius
<style scoped>
p { text-align: center; }
</style>
![height:400px](assets/grts-slide2-flowchart.svg)

<div class="centered"><b>You will not be replaced by an agent...<br>but you may be replaced by someone who can direct one well.</b></div>

<!-- 

There is a reason why it was easy to make small gains in 2024, but it is harder to get the real large gains now.  It requires substantial work, hence this training.

Ask people:
* Have you tried vibe coding?  When did you?  How did it go?
* Do you think that agentic coding will work for you now?  What is still needed?
* Have you ever been a new hire and done work that was completely off base, or supervised an intern that did the same thing?  What was missing?  How was it corrected?
-->

---
# <span class="g">🧭 Guidance</span> <span class="subline">Prompting | Supervision | Hand-holding</span>
<style scoped>
section {
    font-size: 24px;
}
</style>
* Get familiar with the eccentricities of the stupid genius
  * **First steps (concrete, low context, low risk tasks):** Ask it to (1) review your code, (2) debug your software, (3) refactor a class and (4) research the next idea.
* If the agent falls down a rabbit hole 🐰🕳️ -> ask:
  * Research the best 3 approaches to this issue with pros/cons — cite evidence.
  * Check out this site <stack overflow link>.  Does it help?
* If the agent tries to cheat or take a shortcut -> ask:
  * What is the proper way to fix this?
  * Right place for the code? Clean architecture? Utilities library?
* The agent keeps giving me the "average" solution - not the one for my domain!
  * Make the domain explicit: "I am working in this domain and follow such and such guidelines."
  * If possible, use an oracle / golden sample / explicit success criteria.
<div class="centered"><b><i>Takeaway: Spend 1-2 weeks getting a feel for working with the latest LLMs.</b></i></div>

<!--
The first step in this journey is to get to know the stupid genius.
The stupid genius will get lost and do the wrong thing.  They will make foolish mistakes.  There are some simple tasks that only require minimal context (the current file, a few ideas) to work through.  Use these "low context" prompts to get a feel for the leading agents that are available.  

Things to watch out for:
- Confidently wrong / plausible nonsense.
- Hidden constraints (backwards compatibility, encoding, timing, real-time, memory, safety, deployment blast radius).
- Thrashing without a stable hypothesis.
- Tool misuse: wrong command, wrong environment assumptions, partial runs.

Ask:
* Have you spent time trying to get an LLM to work?
* What prompts have you found successful?

-->
---
# <span class="r">🧱 Reality | Rules | Roles</span> <span class="subline">Instructions | Skills | Orientation | Foundation</span>
<style scoped>
section {
    font-size: 24px;
}
</style>
* **.github/copilot-instructions.md** -> Repository orientation
  * Agents will always read this file.  It should contain the fundamentals of the repo, the reality of what it is for, what base technologies are used, how to build and test and how it is structured.
  * Point to any coding standards or guidelines - make them or move them into the repo if needed.
  * Use [this blog post](https://github.blog/ai-and-ml/unlocking-the-full-power-of-copilot-code-review-master-your-instructions-files/) and [this documentation](https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions) for instructions
* **Skills and custom agents** -> wearing different hats
  * Have a repeatable way to focus the agent in on a task or technology.
  * Find the best ones and iterate.  Is the agent getting better at understanding your context>?
  * Use [this repo](https://github.com/github/awesome-copilot) for a curated list of skills and custom agents
* **Keep it concise | Structure matters | Be direct | Show examples**

<div class="centered"><b><i>Takeaway: After bootstrapping the initial set of files, refine them heavily in the first week, putting the best guidance in the relevant places.</b></i></div>

<!--
Shock Claim: As of Dec 2025, the new models are able to hold [8 things in their mind](https://openai.com/index/introducing-gpt-5-2/) at the same time 🤯 - they are limited by the context you give them, not their intelligence.

This is “Orientation” for regulated/legacy work:
- Make “how we work here” explicit so the agent stops guessing conventions.

Concrete assets:
- Repo-wide instructions: `.github/copilot-instructions.md`.
- Optional path-specific instructions: `.github/instructions/*.instructions.md` (backend vs infra vs data, etc.).
- Optional agent instructions: `AGENTS.md` (nearest-file-wins) if you want role-specific behavior.

Roles (practitioner-friendly):
- “Test Writer” (adds/extends oracles).
- “Refactorer” (mechanical changes + proofs).
- “Doc Editor” (runbooks, ADRs, checklists).

Boundaries (regulatory reality):
- Put safety-critical logic, CI/CD, and security configs behind stronger gates.
- Make “may / may not” explicit and require evidence before merge.
Tips
* Keep it concise: Start small - keep it under 1000 lines.
* Structure matters: Use headings and bullet points
* Be direct: Short, imperative rules are more effective than long paragraphs.
* Show examples: Demonstrate concepts with sample code or explanations

-->
---
# <span class="t">🧰 Tools</span> <span class="subline">Capabilities | Abilities | Touch the external world</span>

<style scoped>
section {
    font-size: 22px;
}
</style>


| To get this | use this |
|---|---|
| Issue read and write | [GitHub MCP](https://github.com/github/github-mcp-server), [Atlassian MCP](https://www.atlassian.com/blog/announcements/remote-mcp-server) |
| Up-to-date API | [Context7](https://github.com/upstash/context7) + research online |
| Agent IntelliSense | [Serena](https://oraios.github.io/serena/02-usage/030_clients.html) |
| Deterministic actions | Generate a script for repetitive/complex work (e.g., convert NUnit3 tasks to NUnit4 across many files) |
| Truth sources | diffs, test output, CI checks, benchmarks/sim logs |
| Easy local action | Make VS Code tasks for Build, test, lint, format, etc. |
| Stop the approvals! | **chat.tools.terminal.autoApprove** for git status, list files, get file content |


<div class="centered"><b><i>Takeaway: 1 week - Craft a thoughtful set of MCP tools, VSCode tasks, restrictions and auto-approvals (and update custom agent instructions) to make your "guided, rule-constrained stupid genius" powerful.</b></i></div>

<!--
With rules in place, we can focus on giving power tools to the agent.

With great power comes great responsibility.

Assess the possible failures of each tool and the risks of it being wrong (malware? Lose your secrets? Incorrect GitHub pull requests being created?)  Either:
* Risk too high - don't give access to the tool
* Moderate risk - require explicit approval to run the tool
* Low risk - auto-approve use of the tool

With these tools in place, the agent will be able to do more tasks with fewer tokens, not getting lost as often.
-->

---
# <span class="s">✅ Specifications</span> <span class="subline">Objectives | Checklists | Planning | Requirements</span>

<style scoped>
section {
    font-size: 24px;
}
</style>

For larger, more ambiguous work, spend time planning to reduce churn and wrong turns.

| How large? How ambiguous? | Example | Recommended workflow |
|---|---|---|
| **Level 1 (Low)** | bugs and small edits | we can just make a single prompt |
| **Level 2 (Medium)** | Don't know best way to implement | 1–3 planning prompts (research/explain/3 options) → then implement |
| **Level 3 (High)** | Want the model to follow a specific checklist | Create a checklist in Markdown → review → implement |
| **Level 4 (New feature)** | Significant planning and research needed.  Many steps. | Use [OpenSpec](https://github.com/Fission-AI/OpenSpec) or [Spec Kit](https://github.github.io/spec-kit/): specify → clarify → plan → analyze → implement |

<div class="centered"><b><i>Takeaway: 1-2 weeks - develop a sense of when a model fails and "go to the next level". Choose OpenSpec, Spec Kit, or another platform for large features.</b></i></div>

<!--
Let's waterfall like it's 1999!

Except, that it only takes 5 minutes to 1-2 hours to do all the planning and a few days max to implement the spec.

The power is that you can think through all the decisions, check for inconsistencies and severely reduce churn.

If the agent is misunderstanding the spec, you are able to guide it to update and refine the spec BEFORE implementation.

In many projects, you can review the plan and checklist and trust the tests, model self-description, and smoke testing. This is how you get to a 10x productivity increase with minimal slop.

-->
---
# Final thoughts 1: Don't have AI ruin your codebase

<style scoped>
section {
    font-size: 24px;
}
</style>

Taken from [Deepayan-Thakur's post](https://github.com/orgs/community/discussions/182197#discussioncomment-15283353):
1. Treat AI Agents as Junior Engineers (With Super Speed)
2. Enforce a “Human-in-the-Loop” Merge Contract
3. CI Is Your Real Boss (Make It Ruthless)
4. Security: Assume the Agent Is Overconfident
5. Multi-Agent Setups: Divide Responsibilities or Suffer
6. Maintainability > Cleverness (AI Loves Cleverness)
7. Track Provenance: Know What the AI Touched
8. Teach the Agent Your Rules (Or It Will Make Its Own)

---
# Final thoughts 2: What is at stake

<style scoped>
section {
    font-size: 22px;
}
</style>

Also taken from [Deepayan-Thakur's post](https://github.com/orgs/community/discussions/182197#discussioncomment-15283353):

AI coding agents are not a shortcut to engineering maturity.
They amplify whatever discipline you already have.
* Good processes → insane productivity boost
* Weak processes → faster outages

Use agents to:
* Move faster on the obvious
* Reduce boilerplate
* Explore options

But keep humans accountable for:
* Architecture
* Security
* Taste

# Extra slides
---
# A1: Multi-agent workflows

* You’ll often be waiting on agents. Use that time:
  * Research the next feature in parallel
  * Use [git worktrees](https://git-scm.com/docs/git-worktree) / background agents for parallel branches
  * Delegate to cloud agents (ensure CI/CD is set up)
  * Split roles: Planner → Implementer → Reviewer

<!--
When multi-agent helps:
- Parallel research: API docs, legacy behavior, bug history, test flakiness.
- Separation of concerns reduces thrash and improves review quality.

Practical pattern:
- Planner: decomposes tasks + risks, proposes checkpoints.
- Implementer: makes changes + runs proof.
- Reviewer: checks constraints, safety, and repo conventions.

Implementation tip:
- Git worktrees keep parallel efforts isolated and reduce merge conflicts.
-->

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

<!--
Teach the “3 modes” decision:
- Single prompt: Q&A, small snippet, one-file helper.
- Agent loop: multi-step/multi-file work with plan + evidence gates.
- Human-first: unclear requirements, safety-critical changes, ambiguous bugs without reproduction.

Rule of thumb for regulated/legacy:
- If it changes runtime behavior in a hard-to-test area, treat it as high risk.
- If there’s no oracle, the first deliverable is the oracle (even the unit test that fails - TDD)
-->
---
# A3: Extra References


- [Building effective agents (Anthropic)](https://www.anthropic.com/research/building-effective-agents) — Designing agent loops: checkpoints, tool feedback, stop conditions.
- [About GitHub Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent) — Capabilities, limits, and governance.
- [Security (VS Code Copilot)](https://code.visualstudio.com/docs/copilot/security) — Trust boundaries, tool approvals, prompt injection risks.
- [Tutorial: Work with agents in VS Code](https://code.visualstudio.com/docs/copilot/agents/agents-tutorial) — Local/plan/background/cloud agent workflows + worktrees.
- [Use tools in chat (VS Code) — Tool approval](https://code.visualstudio.com/docs/copilot/chat/chat-tools) — Tool approvals, URL post-approval, and auto-approval tradeoffs.
- [Lessons from Anthropic](https://techwithibrahim.medium.com/the-art-of-agent-prompting-lessons-from-anthropics-ai-team-e8c9ac4db3f3) as of November 2025