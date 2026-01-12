# Copilot coding agent instructions (GRTS)

## What this repository is
This repo contains the **GRTS** slide deck and supporting written material about working with coding agents.

- The **source of truth** for the main deck is a **Marp-flavored Markdown** file.
- The repo also commits **exported artifacts** (PDF + HTML) and a few **static assets** (PNG/SVG).

## Tech + tooling (what you need installed)
- Primary “build tool”: **Node.js + npm/npx**.
- Slide engine: **@marp-team/marp-cli**.
- Diagram tool (optional, only if you edit Mermaid diagrams): **@mermaid-js/mermaid-cli**.

Validated on Windows with:
- `node` v22.20.0
- `npm` v11.6.3
- `@marp-team/marp-cli` v4.2.3 (via `npx`)

## Project layout (where things live)
Repo root:
- `README.md`: quick overview + the canonical export command.
- `GRTS.png`: logo used by the deck.
- `slides/`: primary slide sources and exported artifacts.
- `legacy/`: older/alternate content (reference material; not the Marp source of truth).
- `.vscode/tasks.json`: contains the VS Code “build” task for PDF export.

Slides:
- `slides/GRTS.md`: **source of truth** for the GRTS deck (Marp Markdown).
- `slides/GRTS.pdf`: exported PDF (committed artifact).
- `slides/GRTS.html`: exported HTML (committed artifact).
- `slides/assets/`: diagrams and other deck assets.
  - `slides/assets/grts-slide2-flowchart.mmd`: Mermaid source.
  - `slides/assets/grts-slide2-flowchart.svg`: rendered diagram used by the deck.

## Build / run / validate (copy-paste commands)
### Bootstrap
There is **no `package.json`** in this repo. Do **not** attempt `npm ci`.
- Confirmed failure mode: `npm ci` errors with ENOENT (missing `package.json`).

Instead, use **`npx`** to run tools on-demand:
- `npx --yes @marp-team/marp-cli@latest ...`
- `npx --yes @mermaid-js/mermaid-cli@latest ...` (only if needed)

### Build (export) — PDF (primary)
Preferred: run the VS Code task **Export GRTS slides (PDF)**.

CLI equivalent (works):
- `npx --yes @marp-team/marp-cli@latest slides/GRTS.md --pdf --allow-local-files -o slides/GRTS.pdf`

Notes:
- Always include `--allow-local-files` or the logo/assets referenced by relative paths won’t render.
- Marp will print a warning about insecure local file access when this flag is enabled; that’s expected.

### Build (export) — HTML (secondary)
- `npx --yes @marp-team/marp-cli@latest slides/GRTS.md --html --allow-local-files -o slides/GRTS.html`

If an export is interrupted (e.g., Ctrl+C), just rerun it.

### Assets — regenerate Mermaid SVG (only if you edited the `.mmd`)
- `npx --yes @mermaid-js/mermaid-cli@latest -i slides/assets/grts-slide2-flowchart.mmd -o slides/assets/grts-slide2-flowchart.svg`

Notes:
- `mermaid-cli` may pull in a headless browser dependency on first run; allow extra time.

### Test / lint
- There are no formal automated tests or linters in this repo.
- Validation is primarily: **exports succeed** and the **generated artifacts are up to date**.

## PR hygiene / common expectations
- Treat `slides/GRTS.md` as the canonical source; avoid hand-editing `slides/GRTS.html` / `slides/GRTS.pdf`.
- If you change deck content or assets, regenerate and include the updated outputs:
  - PDF: `slides/GRTS.pdf`
  - HTML: `slides/GRTS.html`
- Keep relative asset paths intact (e.g., the header logo references `../GRTS.png`).

## How to work efficiently (reduce repo searching)
- Start edits in `slides/GRTS.md` unless the user explicitly asks for legacy content.
- Use `.vscode/tasks.json` for the “known good” PDF export command.
- Only search the repo if the instructions above are incomplete or contradict what you observe locally.
