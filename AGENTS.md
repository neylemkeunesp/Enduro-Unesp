# Repository Guidelines

## Project Structure & Module Organization
- `index.html` houses the full game: markup, responsive HUD styles, and JavaScript logic (road generation, physics, audio hooks). Keep new modules inside this file unless a refactor clearly improves clarity.
- Place future assets under `assets/` (sprites, audio) and reference them with relative paths; add `.gitkeep` if the directory would otherwise be empty.
- Prefer splitting large additions into commented regions (e.g., `// --- Input ---`) so contributors can navigate the single-page codebase quickly.

## Build, Test, and Development Commands
- `python3 -m http.server 8000` — Serve the project locally at http://localhost:8000 for browser testing without CORS issues.
- `npx serve .` — Alternative lightweight static server; useful when sharing builds across platforms.
- `npx prettier --write index.html` — Format HTML/CSS/JS before submitting to keep diffs reviewable.

## Coding Style & Naming Conventions
- Use 2-space indentation throughout; align chained calls and object literals for readability.
- Keep JavaScript identifiers in camelCase; reserve SCREAMING_SNAKE_CASE for constants such as `MAX_SPEED`.
- Inline comments remain in Portuguese and should explain gameplay intent (e.g., camera, weather), matching the existing tone.
- When adding CSS, prefer custom properties scoped at the top of `<style>` for colors shared across themes.

## Testing Guidelines
- Automated tests are not present; perform manual regression tests on Chrome and Firefox (desktop) and at least one mobile browser. Validate keyboard and touch controls, audio prompts, and day/night transitions.
- When touching performance-sensitive loops (rendering, physics), enable dev tools performance recording for a one-lap capture and note FPS changes in the PR.
- Document reproduction steps for any bugfix (initial state, controls used, expected vs. actual behavior) in the PR description.

## Commit & Pull Request Guidelines
- Follow the existing subject format: `Área: descrição breve`, written in Portuguese, present tense, and under ~70 characters (e.g., `UI: ajusta layout do painel de status`).
- Rebase on `main` before pushing; keep commits focused on a single concern.
- Pull requests must include: context of the change, screenshots or short clips for UI/gameplay updates, manual test notes, and references to related issues or discussions.
- Signal breaking gameplay changes with a bold "Atenção" note at the top of the PR body so reviewers can prioritize playtesting.
