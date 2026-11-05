# Christoph Hans Portfolio — Website Handoff

Portable notes for whoever edits this site next. Read this before changing page copy, layout, or navigation.

## Project and source files

- This is a plain static site: HTML pages, one shared `styles.css`, and `script.js`. No build step or framework.
- Project pages live in this folder. Their canonical copy sources are the Markdown files one folder above; copy text from those rather than rewriting it:
  - `nakam.html` ← `../100 Nakam.md`
  - `das-rotohr.html` ← `../200 Das Rotohr.md`
  - `elephant-in-the-room.html` ← `../300 Elephant in the Room.md`
  - `yumi.html` ← `../400 YUMI – The whole World.md`
  - `it-takes-balls.html` ← `../500 It Takes Balls.md`
  - `wolken-ueber-luetzerath.html` ← `../600 Wolken über Lützerath.md`
  - `kokain-im-hackenporsche.html` ← `../700 Kokain im Hackenporsche.md`
  - `driving-europe.html` ← `../800 Driving Europe.md`
  - `every-day-is-an-empty-stage.html` ← `../900 Every Day is an Empty Stage.md`
- Keep image references local to this folder and its project asset subfolders. Do not use the parent `_assets` paths in the published pages.
- When using `read_file` output as a patch reference, discard its `LINE|` display prefix; it is not part of the file.

## Site-wide style and responsive rules

- Dark palette; body font Nunito Sans, headings Manrope. Shared color and spacing tokens are at the top of `styles.css`.
- Keep exactly one `.site-footer` in each HTML page.
- Header Instagram mark uses local `instagram-white.png`; preserve its alt text and link.
- The mobile menu is a simple dropdown under the header. `script.js` toggles `.open` and `aria-expanded`; avoid reintroducing the old full-screen overlay or icon animation.
- Work page: no “Work” heading above the grid. Project names are centered, 1.026rem on desktop and the same size on mobile. Desktop grid has three columns; mobile (≤768px) has one column. Vertical gaps are 40px desktop and 55px mobile.
- About: centered, reduced-size intro heading; portrait beside standard-size body copy on desktop, stacked on mobile.
- Contact: centered icon row with the local `contact-instagram.webp` and `contact-email.webp` assets, plus two `☞` glyphs (the first is mirrored). Keep the icon links accessible and retain the Imprint link below the row.

## Project page layout

- Center project titles and metadata.
- After metadata, place the video embed; if there is no video, place the first still in a full-width lead-media slot before synopsis/credits and remove it from the gallery to avoid duplication.
- Desktop video width is about two-thirds of the content width (capped near 720px), centered; mobile video is full width. **Nakam is an exception:** its desktop video is full width.
- Synopsis and credits use equal-width columns with the divider at the exact page midpoint. Preserve the inner gutter on both sides of the divider. On mobile, stack the columns and remove those inner gutters. The user chose a centered divider over equal column heights, so longer credits may extend farther than the synopsis.
- The “CREDITS” heading is intentionally omitted.
- Project navigation runs oldest-to-newest from left to right (the reverse of the Work grid): Nakam → Das Rotohr → Elephant in the Room → YUMI → It Takes Balls → Wolken über Lützerath → Kokain im Hackenporsche → Driving Europe → Every Day is an Empty Stage. Desktop: older/left link on the left, newer/right link on the right. Mobile: newer/right link first and right-aligned, older/left link second and left-aligned; omit the unavailable edge link.
- Desktop galleries retain their mixed-width layouts, except where noted below. On mobile (≤768px), every project still is full content width, stacked vertically.

## Credits convention

- Use `<strong class="talent">` only for real people’s names. Keep roles, institutions, companies, brands, and funding bodies in regular weight. `@hyve.audio` is an explicit exception and remains bold as a talent credit.
- Same-line role/name pairs have exactly two nonbreaking spaces between them. When names start on a new line after `<br>`, put no spaces after the break.
- Use ` · ` between people in name lists; preserve commas in role labels or ordinary prose.
- Chris is credited as **Christoph Hans** in the Editor role on Every Day is an Empty Stage, Driving Europe, Kokain im Hackenporsche, Wolken über Lützerath, It Takes Balls, Elephant in the Room, and Nakam. Das Rotohr already credits Christoph Hans for Script, Editing, Compositing.
- Empty Stage credits are inline role/name pairs. Driving Europe retains its two-line role/name style. Wolken’s first three entries are inline; later entries keep their current grouping. It Takes Balls uses “Director of Photography,” not “DoP.”

## Page-specific media exceptions

- YUMI laurel: two-thirds width on desktop, full width on mobile.
- Driving Europe laurels: three logos in one centered row, scaled evenly so the middle logo is on the page center.
- Das Rotohr laurels: centered and 10% smaller than their previous 280px cap.
- Wolken über Lützerath: synopsis starts at the video’s left edge; laurel is two-thirds width; its three stills are full-width and stacked.
- Elephant in the Room: all five stills, including the lead image, use a centered, non-destructive 2.287:1 crop via CSS; source image files remain unchanged.
- It Takes Balls: preserve the “change language to 👉 OV pls” hint directly below its ARD video, with a gap before the synopsis/credits.

## Preview and publishing status

- Local preview: from this folder run `python3 -m http.server 8000 --bind 127.0.0.1`, then open `http://localhost:8000/`.
- The site has not been published. No GitHub repository has been created and no GoDaddy DNS settings have been changed.
- GitHub Pages can use `christophhans.ch` as the public URL. The free plan generally requires a public repository, so the source files would be visible. GoDaddy remains the domain registrar.
- Before publishing, verify all nine project routes, image loads, menu, footer count, page-turn sequence, and mobile layout.
