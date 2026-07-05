# Middleton Makes Maintenance Notes

Last reviewed: 2026-07-05

These are context notes, not fixes already applied.

## Watch List

- `projects/tensioner.html` says "Page-specific carousel offset rules (9 slides)" but the implemented carousel has 7 radio inputs/slides.
- There are a few visible copy typos worth cleaning when editing nearby text, including "clients specifications".
- `index.html` duplicates a homepage-specific style block instead of using `assets/css/global.css`; that is fine for now, but shared tokens can drift.
- Lightbox JavaScript is duplicated across many project pages. Keep it duplicated for small edits, or extract it only as part of an intentional cleanup.

## QA Checklist For Content Edits

- Serve locally from the repo root and click the edited page, not just `file://`.
- Check the homepage card link, project page nav, and any "Code & resources" links.
- Confirm every referenced image exists in `assets/images/<slug>/`.
- Confirm carousel slide count, radio inputs, labels, thumbnails, and CSS offsets all match.
- Search for placeholders before finishing:

```powershell
rg -n 'YOUR_|placehold|deployable-payload|```html|```$' index.html projects
```

- Search for common absolute/relative asset inconsistencies:

```powershell
rg -n 'src="assets/|href="projects/' index.html projects
```

- Run a whitespace check before committing:

```powershell
git diff --check
```

## Possible Future Cleanup

- Add a tiny shared `assets/js/lightbox.js` and include it from project pages.
- Move homepage styling toward `assets/css/global.css` while preserving the current look.
- Create a reusable carousel snippet or script so slide counts do not require manual CSS offsets.
- Add a simple link/asset checker script if the site grows further.
- Replace placeholder external repo links with the real project repositories or remove the section until code is public.
