# Project Page Template Notes

Use this when adding a new Middleton Makes project page.

## Files To Add Or Update

- Add page: `projects/<slug>.html`.
- Add media: `assets/images/<slug>/hero.jpg` plus `build-1.jpg`, `build-2.jpg`, and optional `thumb-video.jpg`.
- Add homepage card in the right section of `index.html`.

## Recommended Page Sections

1. Header: project name, one-sentence subtitle, and optional `.chip` tags.
2. Hero media: one clear image showing the actual build or result.
3. Overview: what the project is, why it exists, and where it fits into UAV/maker work.
4. My contributions or What I did: specific responsibilities and hands-on work.
5. Technical snapshot or Electronics & hardware: measurable specs, components, software stack, or materials.
6. Workflow/behavior section if the project has control logic, calibration, data flow, or test procedure.
7. Code & resources if links are real and public.
8. Media: carousel with video/images and useful alt text.

## Carousel Checklist

- One radio input per slide.
- One `.carousel__slide` per radio input.
- One thumbnail label per slide, with `for="<radio-id>"`.
- Per-page CSS offset rules must reach `-(slideCount - 1) * 100%`.
- Per-page thumbnail highlight rules must include every thumbnail.
- Use `/assets/images/<slug>/...` root-relative paths.
- Add `class="js-enlarge"` to photos that should open in the lightbox.

## Homepage Card Checklist

Use the existing card pattern:

```html
<article class="card">
  <div class="thumb">
    <img src="/assets/images/<slug>/hero.jpg" alt="<clear project alt text>">
  </div>
  <div class="card-body">
    <h3>Project Name</h3>
    <p>One concrete sentence about what it does.</p>
    <div class="meta">
      <a class="btn" href="/projects/<slug>.html">View project</a>
    </div>
  </div>
</article>
```

## Tone

Keep the writing practical and grounded. The best pages read like a concise build log: what problem existed, what was built, what Graeme did, what tools and materials were used, and what changed after testing.
