# Repository Guidelines

## Project Structure & Module Organization

This repository contains a static, bilingual product designer portfolio.

- `site/dist/` is the editable source directory, despite its name. `index.html` and `finelo.html` load shared `app.js` and `style.css`; there is no build pipeline.
- `site/dist/assets/` stores screenshots, SVG assets, and the downloadable CV.
- `site/previews/` contains visual review screenshots. `site/ASSETS.json` records asset information; `site/VERIFICATION.md` records checks.
- `project-docs/` contains requirements, approved decisions, case copy, storyboards, and source references. Read `project-docs/README.md` before substantive changes.

## Build, Test, and Development Commands

Run commands from the repository root:

```sh
python3 -m http.server 8765 --directory site/dist
node --check site/dist/app.js
git diff --check
```

The server exposes the site at `http://127.0.0.1:8765/`. The other commands check JavaScript syntax and whitespace errors. No package manager, build step, formatter, or lint configuration is currently provided.

## Coding Style & Naming Conventions

Use plain HTML, CSS, and browser JavaScript. Existing files are compact, with many rules and functions on single lines; keep edits focused and avoid unrelated reformatting. Use two spaces when adding multiline blocks. Prefer `const` unless reassignment is necessary, descriptive camelCase JavaScript names, and kebab-case CSS classes and asset filenames.

Provide both Russian and English copy through the existing `t(ru, en)` helper. Preserve language query parameters, accessible labels, image proportions, keyboard interaction, and reduced-motion behavior. Reuse CSS variables for colors and layout values.

## Testing Guidelines

There is no automated test framework or coverage target. For site changes, run the syntax check and inspect both pages in RU and EN at desktop (1440 px) and mobile (390 px) widths. Check overflow, images, navigation, language persistence, lightbox closing, and animation controls when affected. Record actual checks and limitations in `site/VERIFICATION.md`; save useful screenshots in `site/previews/`.

## Commit & Pull Request Guidelines

History currently contains one descriptive initial commit; no enforced convention exists. Use concise, action-oriented messages such as `Fix mobile header spacing`. Keep commits scoped. PRs should describe the change, relevant issue if available, verification performed, and screenshots for visual updates.

## Content & Configuration Rules

Change only requested elements and synchronize affected project documents. Never invent results or attribute other designers’ work to the portfolio owner. Preserve the existing project ID in `site/.openai/hosting.json`; do not create a duplicate Site. Keep credentials and environment files out of Git.
