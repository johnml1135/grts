<p align="center">
	<img src="GRTS.png" alt="GRTS" width="120" />
</p>

# GRTS

## 📄 Slide deck (PDF)
**Download / view:** [slides/GRTS.pdf](slides/GRTS.pdf)

GRTS is a practical system for working with coding agents:

- 🟢 **Guidance** 🧭 — how to prompt and supervise
- 🔴 **Reality / Rules / Roles** 🧱 — how to ground the agent in your repo and constraints
- 🟡 **Tools** 🧰 — how to let the agent take safe, useful actions
- 🔵 **Specifications** ✅ — how to make “done” measurable and reviewable

## Intent 🎯
Help software developers confidently enter the agentic era: getting real leverage from agents while staying safe, correct, and in control.

## Motivation ⚡
> You will not be replaced by an agent, but you may be replaced by someone who can direct one well.

> Vibe coding without a process is like handing over your repo to a drunken robot  🍺🤖!

## Contributing and feedback 💬
This is a learning system. Feedback and improvements are welcome.

Good contributions:
- Tightening language without changing meaning
- Fixing layout/fit issues (especially after content changes)
- Improving examples/checklists while keeping the deck concise
- Adding or refining references (with clear relevance to G/R/T/S)

Good feedback:
- What felt confusing or too abstract
- What was missing to apply this in a real repo
- Where the deck over-promises or under-explains

## Repo contents (where things live) 🗂️
This repository contains the canonical GRTS deck and its assets.

## Source of truth 📌
- Slide deck (Marp): `slides/GRTS.md`
- Exported PDF: `slides/GRTS.pdf`
- Logo: `GRTS.png`
- Deck assets (e.g., diagrams): `slides/assets/`

## Export (PDF) 🖨️
Use the VS Code task **Export GRTS slides (PDF)**, or run:

```bash
npx --yes @marp-team/marp-cli@latest slides/GRTS.md --pdf --allow-local-files -o slides/GRTS.pdf
```

Notes:
- `--allow-local-files` is required for the logo and local assets.
- The deck is intended to use standard Marp features (no custom engines/plugins).
