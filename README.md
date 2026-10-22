# pronova

**Objective:** Bold, conceptual redesign of pronovaengenharia.vercel.app (Pronova Engenharia, renovations in São Paulo, engineer Caio Fernandes), "Sublime style": curtain motion, gorgeous images, almost exaggerated.

**Context:** Caio's request 2026-10-22. Brand kept: Montserrat 200-600, dark warm palette, sand/gold accent. Content and photos come only from the current site (8 works, logo, photo of Caio Fernandes, CREA 5071243724, WhatsApp (13) 98169-7310).

## Working on it
- No build step: open `site/index.html` (or `site/opcao-a/index.html`, `site/opcao-b/index.html`) in the browser.
- Each version is a single HTML file (CSS and JS inside, no libraries). Versions in subfolders (`v2`, `v3`, `v4`, `opcao-a`, `opcao-b`) load images from `../img/` and videos from `../video/`.
- `assets/` holds the files the client sent (originals, untouched). The site uses the optimized copies in `site/img/`.
- Content and photos come only from the client. Don't invent numbers, projects or claims.
- Deploy to the preview URLs is done by Caio for now (see the links below).

## Notes
- Source: `site/index.html` (single file, no libraries). Concept: floor plan draws itself on scroll → opens into the finished room (Kling clip, curtains moving) → headline; manifesto word by word; works on a horizontal rail with curtain reveal; 4 sticky steps; animated portrait (Kling).
- Kling: 2 clips (5 units, 82.5 left): `site/video/sala.mp4`, `site/video/caio.mp4`. Footer says the motion is AI-generated from real photos.
- Preview: https://design.castelluber.com/conceito/pronova/ (noindex). Publish: copy `site/` to `projects/portfolio-showcase/design/conceito/pronova/` and deploy the design project.
- Lighthouse 2026-10-22: mobile 91, desktop 99.

## Versions (2026-10-22, all at /conceito/pronova/<v>/)
- v1: first concept (hero text over a bright photo was too flashy, Caio).
- v2: room opens into a frame on the right, headline on the dark panel; Bodoni Moda headings + Montserrat; film grain; mobile frame sized to the video.
- v3: services strip that runs with scroll; technical line drawing per step; "Ver" cursor + fullscreen viewer that opens with curtains.
- v4: intro (P draws itself, curtain opens; desktop only), eased scroll progress, magnetic buttons. Lighthouse median of 3: mobile 87, desktop 96.

## Client feedback round 1 (2026-10-22): client prefers v1
- Photos: client sent 6 real photos (`assets/original/WhatsApp Image ...` + zip extracted to `assets/zip-2026-10-22/`), max 1600px (WhatsApp compresses). Now `site/img/foto-01..06` (900w + full). Rail = only these 6, in the order sent; the old `obra-*` (upscaled squares, looked low-res on mobile) stay in `img/` only because v2-v4 use them.
- Hero: foto-01 (dining room + kitchen) with a slow CSS zoom; the Kling `sala.mp4` is no longer used in v1 (it was made from the old photo).
- Desktop stutter: geometry measured once (and on resize) instead of reading the layout on every scroll frame; only sections near the viewport update; the room reveal uses transform instead of clip-path (no full-screen repaint); time-based smoothing like v4.
- Context from Caio (not used in the copy, his call): audience is small and medium-sized; the differentiators are the same trusted team for 10+ years, fast delivery and a fair price.
- For max quality, ask the client to send the original files (Drive/email), not via WhatsApp.
- Manifesto ("Por que a Pronova") now has the photo of Caio Fernandes reading the plan (foto-07).
- "Como funciona": Caio did not like the 420vh sticky scroll ("scrolls and does nothing"). Two options, each one a copy of v1 with only that section changed: `site/opcao-a/` (4-step timeline, one screen) and `site/opcao-b/` (photo + list, hover/tap switches the photo, auto-advances). Live at /conceito/pronova/opcao-a/ and /opcao-b/ for feedback. The root v1 still has the old section until one is picked.

## Temporary vercel.app links (2026-10-22, delete when no longer needed)
- https://pronova-conceito.vercel.app/ (v1) and /v2/. Vercel project `pronova-conceito`, deployed from a copy with only v1+v2 (`.tmp/pronova-deploy`, `trailingSlash` + noindex in vercel.json).
