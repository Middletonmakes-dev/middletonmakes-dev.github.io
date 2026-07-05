# Middleton Makes Repo Guide

This is Graeme Middleton's personal project website: a static GitHub Pages portfolio for UAV platforms, electronics, CNC/foam-cutting tools, test rigs, software demos, and mixed maker projects.

## Project Shape

- Stack: plain HTML, CSS, and vanilla JavaScript.
- Hosting: GitHub Pages from the `main` branch of `Middletonmakes-dev/middletonmakes-dev.github.io`.
- Entry point: `index.html`.
- Shared styles: `assets/css/global.css`.
- Project pages: `projects/*.html`.
- Project media: `assets/images/<project-slug>/`.
- There is no package manager, build step, framework, or test runner in this repo.

## Local Preview

Use a static server from the repo root so absolute paths like `/assets/...` resolve correctly:

```powershell
python -m http.server 8000
```

Then open `http://localhost:8000/`.

## Editing Conventions

- Keep the site simple and static unless the user explicitly asks for a build system.
- Prefer shared CSS in `assets/css/global.css` for reusable page styles.
- Keep per-page CSS limited to page-specific carousel offset rules or one-off demo UI needs.
- Use root-relative links for site assets and pages, for example `/assets/images/valk/hero.jpg` and `/projects/valk.html`.
- Put new project images under `assets/images/<slug>/` with predictable names such as `hero.jpg`, `build-1.jpg`, and `thumb-video.jpg`.
- Keep project pages in the existing narrative style: concise overview, concrete contributions, technical snapshot/hardware details, code/resources where relevant, and media.
- Add `class="js-enlarge"` to images that should use the existing lightbox pattern.
- When adding carousel slides, update the radio inputs, thumbnail labels, slide count comments, and per-page `nth-of-type` offset/highlight rules together.

## Design Voice

The site should feel practical, technical, and personal. It is not a marketing landing page. Preserve the dark workshop/lab feel, clear project cards, concrete build details, and first-person maker context.

## Useful Context

Read these before larger edits:

- `.codex/project-context.md` for the repo map and content model.
- `.codex/maintenance-notes.md` for known placeholders, missing assets, and cleanup opportunities.
- `.codex/project-page-template.md` before adding or refreshing a project page.
