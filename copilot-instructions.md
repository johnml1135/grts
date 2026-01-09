# Copilot Instructions (GRTS)

These instructions are for GitHub Copilot (and other coding agents) when working in this repository.

## Mission
Maintain and improve the **GRTS** slide deck and its export artifacts.

Primary goals:
- Keep `slides/GRTS.md` a clean, standard Marp deck (no custom engines/plugins)
- Preserve the deck’s structure and intent while improving clarity and consistency
- Keep exports reproducible (PDF via Marp CLI)

## Source-of-truth files
Treat these as the actively maintained set unless the user explicitly asks otherwise:
- `slides/GRTS.md` (canonical deck)
- `slides/assets/` (deck assets, e.g., diagrams)
- `GRTS.png` (logo)
- `.vscode/tasks.json` (export task)
- `README.md` (repo entry point)
- This file (`copilot-instructions.md`)

## Legacy content (ignore unless asked)
Everything outside the source-of-truth set above should be treated as **legacy**.

Rules:
- Do not edit legacy files/folders unless the user explicitly asks.
- Do not “synchronize” or “clean up” legacy content.
- Do not mention legacy content in `README.md`.

## Marp/export rules
- Use standard `@marp-team/marp-cli`.
- Local assets are required; exporting typically needs `--allow-local-files`.
- Do not introduce custom Marp engines, markdown-it plugins, or build pipelines.

## Style rules (deck)
- Keep slides scannable: prefer short bullets over paragraphs.
- Avoid adding new claims that are not already supported by existing content or explicit sources provided by the user.
- Keep visual/layout changes minimal and intentional.

## Working approach (when changing multiple things)
1. Make a short plan (3–6 steps) if the change is non-trivial.
2. Edit in small, reviewable chunks.
3. Re-export `slides/GRTS.pdf` to validate formatting/layout.
4. Summarize changes and any known limitations.
