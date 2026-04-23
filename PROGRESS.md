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

## Task 6b — Incosmetics Global Case Study ✅

- [x] Add third CaseCard to `client-successes.astro` project index
- [x] Update case index grid to `grid-template-columns: repeat(2, 1fr)` (2×2 — accommodates all 4 cards)
- [x] Create `src/pages/client-successes/incosmetics-global.astro` (created `client-successes/` subdirectory under `pages/`)
- [x] Build Breadcrumb (← Client successes)
- [x] Build page header (eyebrow, H1, body)
- [x] Build top section (2-column: text + meta card with MetricBox — 4 meta items incl. Technology: NFC badge scanning)
- [x] Build body columns (3-column separator grid: challenge / what we did / results)
- [x] Build narrative section ("The full story" — --offwhite bg, H3 + 6 body paragraphs, max-width 720px)
- [x] Build outcomes section (--white bg, H3 + 3 dark metric cells in separator grid using --charcoal background)
- [x] Build role strip
- [x] Build Footer CTA (dark section)
- [x] Add reveal animations to all sections
- [x] Verify: `npm run build` completed — 7 pages built, no errors; `/client-successes/incosmetics-global` in output ✓

---

## Task 6c — RX Global Customer Research Case Study ✅

- [x] Add fourth CaseCard to `client-successes.astro` project index
- [x] Update case index grid to 2×2 layout (`grid-template-columns: repeat(2, 1fr)`)
- [x] Create `src/pages/client-successes/rx-global-research.astro`
- [x] Build Breadcrumb (← Client successes)
- [x] Build page header (eyebrow, H1, body)
- [x] Build top section (2-column: text + meta card with MetricBox — 4 meta items including Agency: The Sound HQ)
- [x] Build body columns (3-column separator grid: challenge / what we did / results)
- [x] Build narrative section (--offwhite bg, H3 + 7 body paragraphs, max-width 720px)
- [x] Build quote section (Chet Burchett quote — --offwhite bg, accent left-border blockquote styling)
- [x] Build outcomes section (--white bg, H3 + 3 dark metric cells: 88% / MRS / 19 on --charcoal bg)
- [x] Build role strip
- [x] Build Footer CTA (dark section)
- [x] Add reveal animations to all sections
- [x] Verify: `npm run build` completed — 7 pages built, no errors; `/client-successes/rx-global-research` in output ✓

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

## Task 11 — Open Graph Meta Tags and Favicon ✅

- [x] All favicon files copied to `public/` root (favicon.ico, favicon-16x16.png, favicon-32x32.png, apple-touch-icon.png, favicon-192x192.png, favicon-512x512.png, site.webmanifest, og-default.png)
- [x] Update `Base.astro` props interface — added `ogTitle`, `ogDescription`, `ogImage`, `ogType` (all optional with defaults)
- [x] Add favicon link tags to `Base.astro` `<head>`
- [x] Add canonical URL link to `Base.astro` `<head>`
- [x] Add Open Graph meta tags to `Base.astro` `<head>`
- [x] Add Twitter Card meta tags to `Base.astro` `<head>`
- [x] Update `<title>` tag to use `{title}` directly (removed `| Allenby Advisory` suffix — full titles now passed from each page)
- [x] Update all 7 pages with correct full titles and descriptions per TASKS_ADDENDUM_META.md
- [x] Verify: `npm run build` completed — 7 pages built in 853ms, no errors

---

## Task 12 — Google Calendar Booking Integration ✅

- [x] Update `Button.astro` — added optional `external` prop; renders `target="_blank" rel="noopener noreferrer"` when `external={true}`
- [x] Update `Nav.astro` — desktop CTA and mobile drawer "Book a consultation" link now points to `https://calendar.app.google/kscewyXr9JDFXDYK8`, opens in new tab
- [x] Update `index.astro` — homepage hero CTA (`#contact`) kept as-is; footer CTA button updated to booking URL with `external={true}`; footer CTA body copy replaced with two new paragraphs per spec
- [x] Update `services.astro` — all three service block buttons + footer CTA button updated to booking URL
- [x] Update `client-successes.astro` — both "Get in touch" buttons + footer CTA button updated to booking URL
- [x] Update `client-successes/incosmetics-global.astro` — top section button + footer CTA button updated to booking URL
- [x] Update `client-successes/rx-global-research.astro` — top section button + footer CTA button updated to booking URL
- [x] Update `about.astro` — "Book a free call" + footer CTA button updated to booking URL
- [x] Update `insights.astro` — footer CTA button updated to booking URL
- [x] Verify: `npm run build` completed — 7 pages built in 924ms, no errors

---

## Task 6d — Global Banking Markets Case Study ✅

- [x] Add fifth CaseCard to `client-successes.astro` project index
- [x] Update case index grid to `grid-template-columns: repeat(3, 1fr)` (3-over-2 layout)
- [x] Create `src/pages/client-successes/global-banking-markets.astro`
- [x] Build Breadcrumb (← Client successes)
- [x] Build page header (eyebrow, H1, body)
- [x] Build top section (2-column: text + meta card with MetricBox — 4 meta items incl. Delivery partner: The Growth Architect; MetricBox: 500+ / Automated workflows in production)
- [x] Build body columns (3-column separator grid: challenge / what we did / results)
- [x] Build narrative section (--offwhite bg, H3 + 8 body paragraphs, max-width 720px)
- [x] No quote section (intentional — no attributed quote in source material)
- [x] Build outcomes section (--white bg, H3 + 3 dark metric cells: 1 / 500+ / Live on --charcoal bg)
- [x] Build role strip (explicitly credits Adam Price and The Growth Architect)
- [x] Build Footer CTA (dark section)
- [x] Add reveal animations to all sections

---

## Task 6e — Clarion AI Assistant Case Study ✅

- [x] Add sixth CaseCard to `client-successes.astro` project index (grid already 3-column — no grid change required)
- [x] Card body uses voice-neutral phrasing: "An AI matchmaking and concierge assistant was developed across seven iterations…"
- [x] Create `src/pages/client-successes/clarion-ai-assistant.astro`
- [x] Build Breadcrumb (← Client successes)
- [x] Build page header (eyebrow, H1, body)
- [x] Build top section (2-column: text + meta card — 4 meta items: Client / Scope / Service type / Delivery partner: Visual Hive; MetricBox: 2025 / TSNN Best Innovation on a B2C show)
- [x] Build body columns — column 2 header reads "What Ade did" (third-person variant)
- [x] Build narrative section: H3 "The full story" + Paras 1–3 (verbatim signed copy) + 7-row iterations table + Paras 4–6 (verbatim signed copy)
- [x] Iterations table: --offwhite header row (ALL CAPS 10px tracked --midgrey), --white body rows, 0.5px --lightgrey row separators, 56px / 220px / 1fr columns; scrolls horizontally on mobile
- [x] Build quote section (full TSNN award citation — US spelling preserved, max-width 620px)
- [x] Build outcomes section (3 dark metric cells: 7 / 57%+ / 77% on --charcoal bg)
- [x] Build role strip (explicitly credits "selection and recommendation of Visual Hive" and "Bogdan Maran's team at Visual Hive reporting into Ade on delivery")
- [x] Footer CTA body reads "Ade would welcome the conversation" (third-person)
- [x] Build Footer CTA (dark section)
- [x] Add reveal animations to all sections
- [x] Verify: `npm run build` completed — 9 pages built, no errors

---

## Future Tasks (Not in Scope)

- [ ] Task 13: Individual article pages under /insights/[slug]
- [ ] Task 14: Contact form
- [ ] Task 15: Deploy to Netlify or Vercel
