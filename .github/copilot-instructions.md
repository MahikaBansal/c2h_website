## Project snapshot

- Type: Small static website (pure HTML/CSS, no build tooling).
- Entry files: `index.html`, `about.html`, `journey.html`, `events.html`, `team.html`, `donate.html`.
- Styles: `css/style.css` (global styles and CSS variables in `:root`).
- Images: `images/` contains site assets (logo used as placeholder in several pages).
- JavaScript: no application JS present in repository root (`js/` exists but empty).

## High-level intent for an AI agent

- Treat this repo as a static brochure site. Changes should preserve the simple header/nav/footer patterns and the existing visual language (bold 2px black borders, rounded buttons, and CSS variables for section colors).
- Prefer minimal, low-risk edits: add pages by copying the header/footer block from `index.html`, reuse CSS variables from `css/style.css`, and avoid introducing complex tooling or new build steps.

## Concrete patterns & examples

- Header / Navigation: all pages use the same header block. When adding a page, copy the header in `index.html` and update the nav link order. Example snippet to reuse: the `<header>` section at the top of `index.html`.
- Page-level styling: global styles live in `css/style.css`. Colors are driven by variables in `:root` (e.g., `--pink`, `--blue`). Use these variables instead of hard-coded hex values when possible.
- “Image placeholder” pattern: many pages use a `.image-placeholder` div or an `<img src="images/logo.jpg">` as a stand-in. Keep file references relative (e.g., `images/logo.jpg`).
- Buttons and controls: site uses 2px solid black borders and hover invert behavior. Follow existing button rules in `css/style.css` to preserve look & feel.

## Developer workflows (discoverable)

- No build, test, or bundler is present — the site is served as static files. For local preview, open `index.html` in a browser or run a simple static server from the project root (e.g., a VS Code Live Server extension or a small HTTP server).
- Avoid adding Node/npm configs, build scripts, or transpilers unless explicitly requested.

## Integration & external dependencies

- Fonts are loaded via Google Fonts links embedded in HTML (`<link href="https://fonts.googleapis.com/...">`). Keep those links intact when editing templates.
- There are no backend services, API keys, or CI integrations referenced in the codebase.

## What to change vs what to avoid

- Change: content text, images, additional static pages, minor CSS improvements using existing variables and selectors.
- Avoid: adding server-side code, adding complex JS frameworks, or removing the simple static-page structure.

## Examples of acceptable edits

- Add a new page `gallery.html`: copy the header/footer from `index.html`, place content between, link `css/style.css`, and add navigation link in the header.
- Improve accessibility: add `alt` text to `<img>` usage and ensure headings exist for each main section (use `<h2>` for section titles).

## Merge guidance (if file already exists)

- Preserve any custom instructions already present. When merging, keep project-specific notes (file references, colors, and header snippet suggestions). If duplicate guidance exists, prefer the more specific note about file paths (e.g., references to `css/style.css`, `index.html`).

## Quick contact / confirmation

If something looks risky (introduce a build step, remove or rename many files, or change the header structure), ask for human confirmation before applying.

---
If this file is unclear or you'd like more rules (linting, commit-message format, preview commands), tell me what to include and I will iterate.
