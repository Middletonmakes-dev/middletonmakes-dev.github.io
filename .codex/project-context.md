# Middleton Makes Project Context

Last reviewed: 2026-07-05

Repository: `Middletonmakes-dev/middletonmakes-dev.github.io`
Default branch: `main`
Site type: static GitHub Pages personal portfolio

## Purpose

Middleton Makes is Graeme Middleton's personal project hub. It presents UAV platforms, electronics, CNC and foam-cutting tools, test rigs, dashboards, and personal maker builds. The strongest material on the site is hands-on engineering work: CAD, composites, 3D printing, ESP32/Arduino electronics, bench testing, UAV integration, and field iteration.

## Audience

Primary readers are people who want to understand Graeme's practical build experience: potential collaborators, employers, clients, other UAV builders, and technically curious makers. The content should make the work inspectable: what was built, what Graeme contributed, what tools and systems were involved, and what the result enabled.

## Current Structure

- `index.html`: homepage and project grid. It currently includes its own inline CSS instead of using `assets/css/global.css`.
- `assets/css/global.css`: shared dark theme, layout, cards, project media, carousel structure, and lightbox styling.
- `projects/`: individual project pages and standalone demo/calculator pages.
- `assets/images/`: project-specific media folders. The local checkout may be sparse, so do not assume images are present locally unless fetched.

## Current Page Inventory

Homepage cards and project pages include:

- UAV platforms: `VALK`, `ENDURA`, `SCOUT`.
- Build/tooling projects: `CNC Hotwire Cutter`, `Dynamic Wire Tensioner`, `UAV Motor Bench Tester`, `Temperature Logger`, `Slow-motion Timer`, `Portal PC`, `Watchdog`, `UAV Launcher`.
- Demo/calculator pages: `tensioner-demo.html`, `uavdashboard.html`, `temp-analyzer-demo.html`, `bungee-calc.html`, `portal-command-center.html`.

The remote tree reviewed on 2026-07-05 contained image folders for `endura`, `hotwire-cutter`, `motor-bench`, `portal-pc`, `scout`, `slowmo-timer`, `tensioner`, `uav-launcher`, `valk`, and `watchdog`; this repo now also includes `temp-logger` media.

## Page Pattern

Most project pages follow this structure:

1. `title`, viewport meta, and shared stylesheet link.
2. Small page-specific `<style>` block for carousel slide offsets and thumbnail highlight rules.
3. Sticky top nav back to homepage anchors.
4. Header with `h1`, subtitle, and sometimes tech chips.
5. Hero media using `/assets/images/<slug>/hero.*`.
6. Narrative sections such as Overview, My contributions, Technical snapshot, Electronics & hardware, Control behaviour, Calibration, Code & resources, and Media.
7. Carousel with radio inputs, slides, thumbnails, embedded YouTube if needed, and `js-enlarge` images.
8. Footer year script and duplicated lightbox script.

Standalone demos differ and may use external CDNs:

- `uavdashboard.html`: Bootstrap and Chart.js motor test demo.
- `tensioner-demo.html`: Font Awesome and custom dashboard UI.
- `bungee-calc.html`: MathJax for launcher equations.
- `temp-analyzer-demo.html`: client-side log parsing/export UI.

## Content Style

Use concrete first-person project context. Prefer "what it does", "what I contributed", and "what hardware/software is involved" over generic portfolio language. Keep descriptions technically specific but readable.

Good recurring details:

- CAD, CNC, composites, resin infusion, wiring, ESP32/Arduino, FreeRTOS, PID, load cells, HX711, KiCad, ArduPilot, iNav, Pixhawk Cube, Matek H743.
- Field/testing context such as launch/recovery, thermal logging, motor thrust testing, cooling changes, and prototype iteration.

## Deployment Model

The site deploys directly from committed static files on GitHub Pages. Avoid adding a build step unless the user explicitly wants a larger redesign. For local QA, run a static server from the repo root because root-relative `/assets/...` paths are used throughout.

## Agent Notes

- This workspace was initialized sparsely to avoid downloading the large image set. HTML/CSS/docs are enough for most context and maintenance work.
- Check `git status` before edits and preserve any user changes.
- A fast first read is usually `rg --files`, then `rg -n '<title>|<h1>|YOUR_|placehold|deployable-payload|```' index.html projects`.
- If adding or validating image references, compare referenced `/assets/images/...` paths with the remote tree or a non-sparse checkout.
