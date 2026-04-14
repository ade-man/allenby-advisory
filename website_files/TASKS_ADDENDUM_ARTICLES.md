# TASKS_ADDENDUM_ARTICLES.md — Insights article pages

This task can be completed at any point after Task 10 (final QA). It builds out the two placeholder article links on the Insights page (`/insights/navigation` and `/insights/data`) into full pages using a new **article layout** — distinct from the existing case study layout.

---

## Task 13 — Insights article pages

**Goal:** Build two long-form article pages at `/insights/navigation` and `/insights/data`, using a shared article layout pattern that matches the rest of the site. Update the Insights page to reflect the navigation article's original publisher.

**Read first:**
- `CONTENT_INSIGHTS_NAVIGATION.md` in full
- `CONTENT_INSIGHTS_DATA.md` in full
- `BRAND.md` Sections 1–4, 7, 12, 14 (colours, type, spacing, borders, eyebrows, dark sections, animations)
- The existing `src/pages/insights.astro` to understand the Articles grid and InsightItem usage

---

### Why this is a new layout (not the case study layout)

Case studies are project records — metric cards, 3-column challenge/what we did/results grids, outcomes strips. Articles are long-form reading. They need a centered single-column reading column, one pullquote, and minimal visual furniture. Do **not** try to adapt the case study page structure.

The article layout shared by both pages:

1. Breadcrumb (← Insights)
2. Article header — eyebrow, H1, standfirst, meta strip (publisher, date where relevant, topic)
3. Article body — single column, max-width 680px, Archivo 16px / line-height 1.8 / --body
4. One pullquote per article, using the existing insights-page pullquote pattern (3px accent left-border, Archivo 20px italic)
5. Related insights — 2-card strip using the existing InsightItem component
6. Footer CTA (dark section, booking link)

The navigation article additionally has a pair of **contrast panels** (expectation vs reality) which is the only bespoke visual element on that page. The data article additionally has **numbered section callouts** with **takeaway pullquote callouts** at the end of each section — these use a light-coloured decorative number (same pattern as the About page engagement list) and an accent-bordered callout box.

---

### Steps

**1. Create the `insights/` subdirectory under `pages/`:**

Astro file-based routing means the URLs `/insights/navigation` and `/insights/data` require files at `src/pages/insights/navigation.astro` and `src/pages/insights/data.astro`. Create the subdirectory.

**2. Update `src/pages/insights.astro`:**

In the Articles grid, update **Article 1 (the navigation article)** so its publisher reads `Trade Show News Network` rather than `allenby-advisory.com`. The title, body and href remain unchanged — the href already points at `/insights/navigation` and becomes live when the new page is created. Article 2 (the data article) requires no changes to the Insights page — its href already points at `/insights/data`.

**3. Create a shared article-body stylesheet block:**

Because both pages share the same body typography, lists, pullquote and related-insights styling, add a block of CSS to `src/styles/global.css` under a comment `/* Article layout — used by /insights/* pages */`. This block should cover:

- `.article-wrap` — centered column, max-width 680px, margin 0 auto
- `.article-body p` — Archivo 400, 16px, line-height 1.8, --body, margin-bottom 18px
- `.article-body h2` — Archivo Condensed 700, 26px, title case, --charcoal, margin-top 48px, margin-bottom 16px
- `.article-body ul` — list-style none, padding 0, margin-bottom 20px
- `.article-body ul li` — padding 8px 0, border-bottom 0.5px solid --lightgrey, padding-left 16px, position relative
- `.article-body ul li:last-child` — border-bottom none
- `.article-body ul li::before` — content "", position absolute, left 0, top 17px, width 4px, height 4px, background --accent
- `.article-pullquote` — margin 40px 0, padding-left 24px, border-left 3px solid --accent
- `.article-pullquote blockquote` — Archivo 20px, italic, --charcoal, line-height 1.45
- `.article-pullquote cite` — 11px, tracked, uppercase, --midgrey, font-style normal, display block, margin-top 12px
- `.article-standfirst` — Archivo 400, 19px, --charcoal, line-height 1.55, margin-bottom 28px
- `.article-meta` — flex row, gap 24px, padding-top 20px, border-top 0.5px solid --lightgrey
- `.article-meta-item` — stacked label/value, gap 4px
- `.article-meta-label` — 9px, tracked, uppercase, --midgrey
- `.article-meta-value` — 11px, tracked, uppercase, --charcoal, font-weight 700
- `.article-meta-value a` — color --accent, text-decoration none

Mobile (`@media (max-width: 768px)`):
- `.article-body p` — 15px
- `.article-body h2` — 22px, margin-top 36px
- `.article-pullquote blockquote` — 17px
- `.article-meta` — flex-direction column, gap 16px
- Section padding reduced to `48px 20px`

**4. Build `src/pages/insights/navigation.astro`:**

Follow `CONTENT_INSIGHTS_NAVIGATION.md` exactly. Build sections in order:

- Breadcrumb
- Article header (--white bg): eyebrow, H1, standfirst, meta strip
- Article body (--offwhite bg): opening paragraphs → contrast panels → post-panel paragraph → "What your visitors actually need" H2 and list → pullquote → "Don't abandon the analogue" H2 → "Navigation is an investment" H2
- Related insights (--white bg): 2-card grid using InsightItem
- Footer CTA (dark section)

**Contrast panels implementation:** 2-column CSS grid, gap 0.5px, parent bg --lightgrey, each panel --white bg with padding 28px. On max-width 768px, stack to single column. This is the only bespoke component on this page — build it inline in the page, not as a reusable component.

The TSNN publisher link on the meta strip opens in a new tab (`target="_blank" rel="noopener noreferrer"`).

**5. Build `src/pages/insights/data.astro`:**

Follow `CONTENT_INSIGHTS_DATA.md` exactly. Build sections in order:

- Breadcrumb
- Article header (--white bg): eyebrow, H1, standfirst, meta strip (no external publisher link on this one)
- Article body (--offwhite bg): introduction → "Getting started" H2 → Section 01 (numbered) → Section 02 (numbered) → Section 03 (numbered with two takeaway callouts) → pullquote → "In summary" H2
- Related insights
- Footer CTA

**Numbered sections implementation:** Each section starts with a flex row containing a large decorative number (Archivo Condensed 700, 48px, --lightgrey) and a heading (Archivo Condensed 700, 26px, --charcoal). Same pattern as the About page engagement list — inline in the page, not a reusable component.

**Takeaway callouts implementation:** Each numbered section ends with one or (for Section 03) two callout boxes. Each callout: --white bg, border-left 3px solid --accent, padding 16px 20px, margin 24px 0 8px. Preceded by a "Takeaway" label in ALL CAPS, 10px tracked, --midgrey. Typography inside: Archivo 15px, --charcoal, line-height 1.55, not italic (distinguishing takeaways from the pullquote).

**6. Reveal animations:**

Apply `class="reveal"` per the animation notes at the end of each content file. The above-the-fold elements (breadcrumb, article header, opening paragraphs) render immediately without reveal classes.

**7. Update the insights page Article 1 publisher:**

In `src/pages/insights.astro`, the navigation article card currently shows `allenby-advisory.com` as publisher. Change to `Trade Show News Network`. Leave title, body and href unchanged.

---

### Verification

1. `/insights/navigation` renders all sections correctly
2. `/insights/data` renders all sections correctly
3. On the Insights page, the first article card shows "Trade Show News Network" as publisher
4. Both article routes are navigable from the Insights page cards (no 404)
5. Breadcrumbs on both pages link back to `/insights`
6. The TSNN link in the navigation article's meta strip opens in a new tab; the "Developing a 1-2-1 meetings strategy" link in both articles' related insights grids opens in a new tab; all other internal links stay in the same tab
7. Contrast panels on the navigation article render as two side-by-side panels on desktop, stacked on mobile (≤768px)
8. Numbered sections on the data article show large --lightgrey numbers (48px) alongside headings; takeaway callouts have accent left-borders
9. One pullquote per article, styled consistently with the Insights page featured pullquote
10. Related insights grids show two cards each, using the existing InsightItem component
11. Footer CTA "Book a free 30-minute call" button opens Google Calendar booking link in a new tab on both pages
12. Body text is --body (#2e2d2b), reading column is max-width 680px, centered
13. H2s are title case Archivo Condensed 700 — NOT all caps — on both pages
14. US English spelling preserved throughout the navigation article ("organizers", "familiarize", "realize", "orienting"); UK English used throughout the data article ("organisers", "behavioural", "socialising", "metre", "programme")
15. Mobile layout: reading column fits viewport, no horizontal overflow, contrast panels stack, meta strip stacks vertically
16. `npm run build` completes without errors
