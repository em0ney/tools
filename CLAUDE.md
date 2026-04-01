# CLAUDE.md — Guide for Building Tools Here

This repo is a collection of single-file HTML+JavaScript tools served via GitHub Pages.
Inspired by Simon Willison's approach: https://simonwillison.net/2025/Dec/10/html-tools/

## Core Rules

1. **One file per tool.** All HTML, CSS, and JS live in a single `.html` file. No separate assets, no build step, no bundler.
2. **No React, no frameworks with build steps.** Vanilla JS only, or libraries loaded from a CDN (cdnjs, jsDelivr). JSX is not allowed.
3. **Keep files small.** Target a few hundred lines. Maintainability matters less at this scale; simplicity matters more.
4. **Self-contained.** A tool must work by opening the file directly in a browser — no server required.

## File Naming

- Lowercase kebab-case: `keyboard-debug.html`, `json-formatter.html`
- Descriptive and specific. Avoid generic names.

## State & Storage

- **URL hash/params** for shareable, bookmarkable state (small data).
- **localStorage** for larger state or secrets (API keys, user preferences). Never hardcode secrets.

## UI Patterns

- Mobile-friendly by default (`<meta name="viewport" ...>`).
- Include a "Copy to clipboard" button where output is text.
- Support `<input type="file">` for file input — no server uploads.
- Provide download functionality for generated files using Blob URLs.

## External APIs

- Prefer CORS-enabled public APIs (GitHub, PyPI, Bluesky, etc.).
- For LLM APIs (Anthropic, OpenAI), prompt the user to enter their API key and store it in localStorage.

## Adding a New Tool

1. Create `tool-name.html` in the repo root.
2. Add a link + description to `index.html`.
3. Test by opening the file directly in a browser before committing.

## Reference Implementation

`keyboard-debug.html` is the canonical reference. Read it before building a new tool.
