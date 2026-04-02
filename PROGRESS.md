# Allenby Advisory Website — Build Progress

Track progress on each task. Mark items `[x]` as they are completed.

---

## Task 1 — Project Initialisation ✅

- [x] Run `npm create astro@latest allenby-advisory` and install dependencies
- [x] Update `astro.config.mjs` with static output and site URL
- [x] Create full folder structure (components, layouts, pages, styles, public/fonts, public/images)
- [x] Create `global.css` — CSS custom properties (colours + spacing)
- [x] Create `global.css` — base reset and body styles
- [x] Create `global.css` — utility classes (.font-brand, .font-display, .font-label, .font-body)
- [x] Create `global.css` — patterns (.grid-separator, .dark-section, .reveal, .skill-pill, .section-label, @keyframes slideUp, .animate-slide-up)
- [x] Verify: `npm run build` completes without errors

---

## Task 2 — Base Layout & Shared Components ✅

- [x] Create `Base.astro` layout (head, Google Fonts link, ClientRouter, global.css import, slot)
- [x] Create `Nav.astro` (logo, nav links, CTA, active state via Astro.url.pathname)
- [x] Create `Footer.astro` (brand name, copyright)
- [x] Create `Button.astro` (primary / ghost / light variants)
- [x] Create `SectionLabel.astro` (eyebrow component)
- [x] Verify: index page builds and renders Nav + Footer correctly

---

## Task 3 — Reusable Content Components ✅

- [x] Create `ServiceTile.astro` (number, category, title, body, href)
- [x] Create `CaseCard.astro` (result badge, title, event tag, body, href)
- [x] Create `Testimonial.astro` (quote, name, role)
- [x] Create `MetricBox.astro` (number, description)
- [x] Create `InsightItem.astro` (type, title, body, publisher, href)
- [x] Add Intersection Observer scroll-reveal script to `Base.astro`
- [x] Verify: all components build without errors

---

## Task 4 — Homepage ✅

- [x] Build Hero section (H1, subtitle, CTA)
- [x] Build "Who this is for" section (audience box with accent border)
- [x] Build "What we do" section (3 ServiceTile components in grid)
- [x] Build Network strip (dark section with skill pills)
- [x] Build "Recent work" section (2 CaseCard components)
- [x] Build "What clients say" section (2 Testimonial components)
- [x] Build Insights section (3 InsightItem components)
- [x] Build Footer CTA (dark section, id="contact")
- [x] Add reveal classes and transition:animate to appropriate elements
- [x] Verify: all sections render, scroll animations trigger, no console errors

---

## Task 5 — Services Page ✅

- [x] Build page header (eyebrow, H1, body text)
- [x] Build Service block 1 — Advisory (id="advisory", 2-column layout)
- [x] Build Service block 2 — Delivery (id="delivery")
- [x] Build Service block 3 — Engagement (id="engagement")
- [x] Build Capabilities grid (4-column, separator technique, 8 cells)
- [x] Build Footer CTA
- [x] Verify: all blocks render, capability grid is 4-column, anchor links work

---

## Task 6 — Client Successes Page ✅

- [x] Build page header
- [x] Build project index (2 CaseCards linking to anchors)
- [x] Build Case study 1 — EquipHotel (top section, body columns, quote, role strip)
- [x] Build Case study 2 — Imbibe Live (top section, body columns, quote, role strip)
- [x] Build Footer CTA
- [x] Verify: anchor links #equiphotel and #imbibe work, MetricBox renders correctly

---

## Task 7 — About Page ✅

- [x] Build Hero split (2-column: text left, credential card right with "AA" avatar)
- [x] Build "The team" section (eyebrow, H2, body, 3-column grid)
- [x] Build "Flexible" section (2-column: text left, numbered engagement list right)
- [x] Build Footer CTA
- [x] Verify: credential card avatar shows "AA", numbered list with decorative numbers renders

---

## Task 8 — Insights Page ✅

- [x] Build page header (eyebrow, H1, body)
- [x] Build featured article (2-column: article info left, pullquote right)
- [x] Build articles grid (3 InsightItem components, separator technique)
- [x] Build Speaking, podcasts and panels list (3-column grid rows)
- [x] Build Footer CTA
- [x] Verify: all external links open in new tab, featured pullquote renders side by side

---

## Task 9 — Responsive Mobile Layout ✅

- [x] Adjust hero H1 font-size (52px → 34px) on all pages (done inline per page)
- [x] Stack all 2-column layouts to single column (done inline per page)
- [x] Stack all 3-column grids to single column (done inline per page)
- [x] Adjust 4-column capability grid to 2-column (done in services.astro)
- [x] Stack case study top section (done in client-successes.astro)
- [x] Stack insights featured article (done in insights.astro)
- [x] Mobile nav hamburger JS updated to use `astro:page-load`, closes drawer on link click
- [x] Global mobile overrides added to global.css — section-inner and dark-section padding reduced to 48px 20px

---

## Task 10 — Animation Polish & Final QA ✅

- [x] View Transitions (fade) — ClientRouter active; scroll reveal re-initialises on `astro:page-load`
- [x] Hero H1 slide-up animation — `animation-fill-mode: both` confirmed in global.css `.animate-slide-up`
- [x] Scroll reveals — `reveal` class added to ServiceTile, CaseCard, Testimonial component roots; InsightItem already had it
- [x] Stagger delays — `transition-delay` applied globally to `.grid-separator > *:nth-child()` (up to 8 items)
- [x] Link audit — nav links ✓, service tile links ✓, case card links ✓, external links ✓, CTA buttons fixed (href="#" → href="/#contact"), email link ✓
- [x] Typography audit — "Three Ways We Work." fixed (was lowercase); all H1/H2/H3 title case confirmed; nav/eyebrows/tags ALL CAPS via CSS; body sentence case ✓
- [x] Colour audit — all body text uses --body (#2e2d2b) ✓, --midgrey only for labels/captions ✓, accent used correctly ✓
- [x] InsightItem external link detection — `target="_blank"` now only applied to external (http) links
- [x] `npm run build` — completed in 781ms, 5 pages built, no errors

---

## Future Tasks (Not in Scope)

- [ ] Task 11: Open Graph meta tags and favicon
- [ ] Task 12: Calendly embed / booking widget
- [ ] Task 13: Individual article pages under /insights/[slug]
- [ ] Task 14: Contact form
- [ ] Task 15: Deploy to Netlify or Vercel
