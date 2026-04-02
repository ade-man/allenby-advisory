# TASKS.md — Sequential Build Tasks for Cline

Complete tasks in order. Do not start the next task until the current one passes its verification check. Each task is scoped to keep Cline well within token limits.

**Before starting any task:** Read `CLINE_INSTRUCTIONS.md` and `BRAND.md` in full.

---

## Task 1 — Project initialisation

**Goal:** Create the Astro project with correct configuration and dependencies.

**Steps:**

1. In your terminal, run:
```bash
npm create astro@latest allenby-advisory -- --template minimal --no-install --no-git
cd allenby-advisory
npm install
```

2. Install the View Transitions package (already included in Astro 4, no extra install needed).

3. Update `astro.config.mjs`:
```js
import { defineConfig } from 'astro/integration';

export default defineConfig({
  output: 'static',
  site: 'https://www.allenby-advisory.com',
});
```

4. Create the full folder structure as specified in `CLINE_INSTRUCTIONS.md`.

5. Create `src/styles/global.css` with:
   - All CSS custom properties from BRAND.md Section 1 (colours) and Section 3 (spacing)
   - Base reset: `*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }`
   - Base body styles: font-family Archivo, background --offwhite, color --body, font-size 15px, line-height 1.7
   - All utility classes from BRAND.md Section 2 (.font-brand, .font-display, .font-label, .font-body)
   - The `.grid-separator` pattern from BRAND.md Section 4
   - The `.dark-section` pattern from BRAND.md Section 12
   - The `.reveal` and `.is-visible` scroll animation classes from BRAND.md Section 14
   - The `.skill-pill` class from BRAND.md Section 16
   - The `@keyframes slideUp` and `.animate-slide-up` classes from BRAND.md Section 14
   - The `.section-label` class from BRAND.md Section 7

**Verification:** Run `npm run dev`. Site starts without errors. No pages exist yet — that's fine.

---

## Task 2 — Base layout and shared components

**Goal:** Build the Base layout, Nav, and Footer components.

**Read first:** BRAND.md Sections 5, 13, 14.

**Steps:**

1. Create `src/layouts/Base.astro`:
   - Props: `title: string`, `description: string`
   - `<head>` includes: charset, viewport, title, meta description, Google Fonts link (from BRAND.md Section 2), import of global.css
   - `<head>` includes: `<ViewTransitions />` from 'astro:transitions'
   - `<body>`: `<slot />` inside

2. Create `src/components/Nav.astro`:
   - No props
   - Use `Astro.url.pathname` to detect active page
   - Structure: `<nav>` containing logo span (Julius Sans One), `<ul>` of nav links, CTA anchor
   - Active state: add class `nav-active` when pathname matches the link's href
   - Links: / (not in nav — logo is home), /services, /client-successes, /about, /insights
   - CTA: "Book a consultation" → href: "/#contact"
   - Full CSS per BRAND.md Section 5

3. Create `src/components/Footer.astro`:
   - No props
   - Full CSS per BRAND.md Section 13

4. Create `src/components/Button.astro`:
   - Props: `label: string`, `href: string`, `variant?: 'primary' | 'ghost' | 'light'` (default: 'primary')
   - Full CSS per BRAND.md Section 6

5. Create `src/components/SectionLabel.astro`:
   - Props: `text: string`
   - Full CSS per BRAND.md Section 7

**Verification:** Create a temporary `src/pages/index.astro` that imports Base, Nav and Footer and renders "Hello". Confirm nav and footer render correctly in the browser.

---

## Task 3 — Reusable content components

**Goal:** Build all reusable content components before building any pages.

**Read first:** BRAND.md Sections 8, 9, 10, 11.

**Steps:**

1. Create `src/components/ServiceTile.astro` — per BRAND.md Section 8

2. Create `src/components/CaseCard.astro` — per BRAND.md Section 9

3. Create `src/components/Testimonial.astro` — per BRAND.md Section 10

4. Create `src/components/MetricBox.astro` — per BRAND.md Section 11

5. Create `src/components/InsightItem.astro`:
   - Props: `type: string`, `title: string`, `body: string`, `publisher?: string`, `href: string`
   - Structure: tag (ALL CAPS badge, 0.5px border --lightgrey), H3 (Archivo Condensed 700, title case, 18px), body text (13px --body), publisher (11px tracked uppercase --midgrey)
   - Add `reveal` class for scroll animation

6. Add the Intersection Observer scroll reveal script to `Base.astro` — paste the script block from BRAND.md Section 14 in a `<script>` tag before `</body>`.

**Verification:** Temporarily use each component in the index page to confirm they render with correct styles.

---

## Task 4 — Homepage

**Goal:** Build the complete homepage.

**Read first:** CONTENT_HOME.md in full. BRAND.md Sections 12, 14.

**Steps:**

1. Replace `src/pages/index.astro` with the full homepage.

2. Import all components needed: Base, Nav, Footer, SectionLabel, ServiceTile, CaseCard, Testimonial, InsightItem, Button.

3. Build each section in order as specified in CONTENT_HOME.md:
   - Hero
   - Who this is for
   - What we do (3 service tiles)
   - Network strip (dark section)
   - Recent work (2 case cards)
   - What clients say (2 testimonials)
   - Insights (3 insight items)
   - Footer CTA (dark section, id="contact")

4. Apply `transition:animate="fade"` to the hero H1.

5. Add `class="reveal"` to: audience box, each service tile, each case card, each testimonial, each insight item, the network strip, the skill pills row.

6. Skill pills: hardcode inline in the page (not a component) as a flex-wrap row of `<span class="skill-pill">` elements.

**Verification:** All sections render. Scroll animations trigger. No console errors. Body text is dark (#2e2d2b), not grey.

---

## Task 5 — Services page

**Goal:** Build the Services page.

**Read first:** CONTENT_SERVICES.md in full.

**Steps:**

1. Create `src/pages/services.astro`.

2. Import: Base, Nav, Footer, SectionLabel, Button.

3. Build sections in order:
   - Page header (eyebrow, H1, body)
   - Service block 1 (id="advisory") — 2-column layout, hardcoded inline (not a component — each block has unique copy)
   - Service block 2 (id="delivery")
   - Service block 3 (id="engagement")
   - Capabilities grid (4-column, separator technique, 8 cells)
   - Footer CTA (dark section)

4. Service block layout: CSS grid `grid-template-columns: 200px 1fr`, border-bottom between blocks.

5. Fit list items: `<ul>` with custom CSS — no bullets, each item has a 4px accent dot via `::before` pseudo-element, border-bottom between items.

6. How it works strip: `<div>` with --offwhite bg, 0.5px border, padding 12px 16px.

7. Add `class="reveal"` to each service block and each capability grid cell.

**Verification:** All 3 service blocks render. Capability grid is 4-column. Anchor links #advisory, #delivery, #engagement work.

---

## Task 6 — Client Successes page

**Goal:** Build the Client Successes page including both full case studies.

**Read first:** CONTENT_CLIENT_SUCCESSES.md in full. BRAND.md Sections 9, 11.

**Steps:**

1. Create `src/pages/client-successes.astro`.

2. Import: Base, Nav, Footer, SectionLabel, CaseCard, MetricBox, Button.

3. Build sections in order:
   - Page header
   - Project index (2 CaseCards)
   - Case study 1 (id="equiphotel"):
     - Top section (2-column: text + meta card)
     - Body columns (3-column separator grid)
     - Quote section
     - Role strip
   - Case study 2 (id="imbibe"):
     - Top section
     - Body columns
     - Quote section
     - Role strip
   - Footer CTA

4. Meta card: --offwhite bg, 0.5px border, padding 22px. Use MetricBox component for the metric.

5. Body column headers (The challenge / What we did / The results): ALL CAPS, 11px, tracked, --midgrey.

6. Quote blockquotes: Archivo 16px, italic, --charcoal, border-left 3px solid --accent.

7. Add `class="reveal"` to: both CaseCards, each case study section.

**Verification:** Both case studies render. Anchor links #equiphotel and #imbibe work. MetricBox shows correctly.

---

## Task 7 — About page

**Goal:** Build the About page.

**Read first:** CONTENT_ABOUT.md in full.

**Steps:**

1. Create `src/pages/about.astro`.

2. Import: Base, Nav, Footer, SectionLabel, Button.

3. Build sections in order:
   - Hero split (2-column: text left, credential card right)
   - The team (eyebrow, H2, body, 3-column grid)
   - Flexible section (2-column: text left, numbered list right)
   - Footer CTA

4. Credential card: 0.5px border, padding 28px. Avatar: 56×56px square, --charcoal bg, Julius Sans One "AA". Name: Julius Sans One 17px. Title: ALL CAPS 11px tracked --midgrey. Bio items: flex row, 4px accent dot, border-bottom between items.

5. Numbered engagement list: decorative numbers in Archivo Condensed 700 24px --lightgrey (not a functional list number — just decorative large text). Item labels in ALL CAPS 11px tracked.

6. Add `class="reveal"` to: credential card, team grid cells, engagement list items.

**Verification:** Two-column hero splits correctly. Credential card avatar shows "AA". Numbered list renders with large decorative numbers.

---

## Task 8 — Insights page

**Goal:** Build the Insights page.

**Read first:** CONTENT_INSIGHTS.md in full.

**Steps:**

1. Create `src/pages/insights.astro`.

2. Import: Base, Nav, Footer, SectionLabel, InsightItem, Button.

3. Build sections in order:
   - Page header
   - Featured article (2-column: article info left, pullquote right) — --white bg
   - Articles grid (3 InsightItem components, separator technique)
   - Speaking, podcasts and panels (list, each row is 3-column grid)
   - Footer CTA

4. Featured pullquote: border-left 3px solid --accent, padding-left 20px. Blockquote: Archivo 18px italic --charcoal.

5. Appearances list item layout: `grid-template-columns: 80px 1fr auto`. Type badge: bg --charcoal, white text, 10px tracked uppercase.

6. All external links: add `target="_blank" rel="noopener noreferrer"`.

7. Add `class="reveal"` to: featured section, each article card, each appearance item.

**Verification:** Featured article and pullquote render side by side. 3 article cards in grid. 3 appearance items in list. All external links open in new tab.

---

## Task 9 — Responsive mobile layout

**Goal:** Make all pages responsive for mobile (max-width 768px).

**Read first:** BRAND.md Section 15.

**Steps:**

Add a `@media (max-width: 768px)` block to `global.css` covering:

1. **Nav:** Hide nav links and CTA. Show hamburger menu button. Add JS toggle for mobile menu drawer (inline `<script>` in Nav.astro). Drawer: full-width, --charcoal bg, links stacked vertically.

2. **Hero H1:** font-size reduce from 52px to 34px.

3. **All 2-column layouts** (homepage audience box area, services page service blocks, about hero, about flexible section): `grid-template-columns: 1fr` — stack vertically.

4. **3-column grids** (service tiles, insight items, team grid): `grid-template-columns: 1fr` — single column.

5. **4-column capability grid:** `grid-template-columns: 1fr 1fr` — two columns.

6. **2-column case card grid:** `grid-template-columns: 1fr` — single column.

7. **Service blocks** (services page): Remove the 200px fixed left column. Stack label col above content col.

8. **Case study top section:** Stack meta card below text on mobile.

9. **Section padding:** Reduce from `72px 40px` to `48px 20px`.

10. **Featured article** (insights): Single column, pullquote below article info.

**Verification:** Resize browser to 375px width. All pages readable. No horizontal overflow. Nav hamburger works.

---

## Task 10 — Animation polish and final QA

**Goal:** Refine animations, check all links, final cross-browser check.

**Steps:**

1. **View Transitions:** Confirm page-to-page navigation uses the fade transition (from ViewTransitions component). Test by clicking each nav link.

2. **Hero animation:** Confirm H1 slides up on first load. Add `animation-fill-mode: both` to prevent flash.

3. **Scroll reveals:** Test each page — all `.reveal` elements should animate in as you scroll down. Confirm no elements are invisible on load (check initial state is `opacity: 0, transform: translateY(20px)`).

4. **Stagger delays:** Confirm service tiles, capability grid cells, and team grid cells stagger (0s, 0.1s, 0.2s). Add `nth-child` delays in global.css if not already done.

5. **Link audit — check every link resolves:**
   - Nav: /, /services, /client-successes, /about, /insights
   - Homepage service tiles: /services#advisory, /services#delivery, /services#engagement
   - Homepage case cards: /client-successes#equiphotel, /client-successes#imbibe
   - Insights page: all external links open in new tab
   - All "Book a consultation / call" buttons: point to /#contact (or Calendly URL if provided)
   - Email link: ade@allenby-advisory.com

6. **Typography audit — check every page:**
   - Page H1, section H2, card H3: title case, Archivo Condensed 700 — NOT all caps
   - Nav links, eyebrows, tags, badges, CTAs, metadata: ALL CAPS
   - Body text: sentence case, Archivo 400, color #2e2d2b (not grey)
   - Brand name (nav logo, footer): Julius Sans One

7. **Colour audit:**
   - No body text in --midgrey (#888780) — only labels, captions, metadata
   - Accent --accent (#2C5F8A) used max once per section
   - Dark sections: correct bg (--charcoal), body text (#c8c6c2)

8. **Build check:** Run `npm run build`. Fix any build errors. Run `npm run preview` and test the production build.

**Verification:** `npm run build` completes without errors. All 5 pages render in preview. No broken links. No console errors.

---

## Future tasks (not in scope for initial build)

These can be addressed in a later session:

- **Task 11:** Add Open Graph meta tags and favicon
- **Task 12:** Add a Calendly embed or booking widget to replace the `/#contact` placeholder
- **Task 13:** Add individual article pages under `/insights/[slug]`
- **Task 14:** Add a contact form as an alternative to the email link
- **Task 15:** Deploy to Netlify or Vercel
