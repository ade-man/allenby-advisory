# TASKS_ADDENDUM_OBJECTIVES.md — Case studies by objective section

This task can be completed at any point after the existing Client Successes page is built and verified. It adds a new editorial section to `/client-successes` and relabels the existing card grid.

---

## Task 14 — Add "What are you trying to achieve?" section to Client Successes page

**Goal:** Add a static editorial section above the existing card grid on `/client-successes`, grouping case studies by the kind of outcome they represent. Relabel the existing card grid section to position it as the full catalogue. No filter UI, no JavaScript interaction — this is a curated, always-visible block of linked case study references.

**Read first:**
- `CONTENT_CLIENT_SUCCESSES_OBJECTIVES.md` in full
- `BRAND.md` Sections 1–4, 7, 14 (colours, type, spacing, borders, eyebrows, animations)
- The existing `src/pages/client-successes.astro` to understand the current structure

---

### Why this change

The Client Successes page currently works as a directory (card grid) but the page then deep-dives into only two case studies (Equiphotel and Imbibe). The directory alone gives every case study the same visual weight regardless of fit with a visitor's needs. A "by objective" editorial layer gives prospects a second, curated way into the work — phrased around the outcomes they're trying to achieve rather than the client names they recognise.

---

### Steps

**1. Update `src/pages/client-successes.astro` page order:**

Insert the new objectives section between the page header and the existing card grid. The final page order is:

1. Page header (unchanged)
2. **Objectives section** (NEW — build this)
3. Card grid (existing — only change is the label, see step 3)
4. Equiphotel case study (existing — unchanged)
5. Imbibe case study (existing — unchanged)
6. Footer CTA (unchanged)

**2. Build the objectives section:**

Use a `<section class="objectives-section" id="objectives">` wrapper. Inside:

- `SectionLabel` component with text "Case studies by objective"
- `<h2>` — "What are you trying to achieve?"
- `<p class="objectives-intro">` — the intro paragraph from the content spec
- Five `<div class="objective-row">` blocks, one per objective, each containing:
  - Left column: eyebrow `<span>` (ALL CAPS) + `<h3>`
  - Right column: `<div class="objective-refs">` containing one or more `<div class="objective-ref">` blocks

Each `.objective-ref` contains:
- `<a class="objective-ref-client" href="...">` — the client name, linked to the case study
- `<span class="objective-ref-hook">` — the one-line hook
- `<span class="objective-ref-badge">` — the result badge

Content is specified in full in `CONTENT_CLIENT_SUCCESSES_OBJECTIVES.md`.

**3. Relabel the existing card grid section:**

The current label "All projects" becomes "Browse all client successes". Leave all cards, hrefs and the grid layout exactly as they are.

Add `border-top: 0.5px solid var(--lightgrey)` above the relabelled section if it doesn't already have one, to visually separate the card grid from the objectives section above it.

**4. Add CSS to `src/styles/global.css`:**

Paste the full CSS block from `CONTENT_CLIENT_SUCCESSES_OBJECTIVES.md` (the block under the comment `/* Objectives section — used on Client Successes page */`) into global.css. Place it alongside other page-specific styles — after the base utility classes, before any mobile `@media` block that already exists (the mobile override for `.objective-row` is included in the spec and should sit inside your existing `@media (max-width: 768px)` block, or as its own block if easier).

**5. Link audit:**

All links in the objectives section point to existing, live routes:

- Incosmetics Global → `/client-successes/incosmetics-global`
- Clarion Events → `/client-successes/clarion-ai-assistant/`
- Equiphotel Paris → `/client-successes#equiphotel`
- Imbibe Live London → `/client-successes#imbibe`
- RX Global → `/client-successes/rx-global-research`
- Global Banking Markets → `/client-successes/global-banking-markets/`

Implement each link with the href exactly as specified. Note the trailing slashes on the Clarion and GBM routes — preserve them as written.

**6. Reveal animations:**

Apply `class="reveal"` to each `.objective-row`. The section header block (eyebrow, H2, intro paragraph) can use `class="reveal"` as well since it may be below the fold depending on browser height.

---

### Verification

1. `/client-successes` renders in the order: page header → objectives section → card grid → Equiphotel case study → Imbibe case study → footer CTA
2. Objectives section shows five stacked rows: left column has eyebrow + H3, right column has 1–2 linked case study references with client name, hook text and result badge
3. On desktop, each row uses a 280px left column + flexible right column grid with 48px gap
4. On mobile (≤768px), each row stacks to a single column with 20px gap
5. Between objective rows: 0.5px solid --lightgrey border-bottom; last row has no bottom border
6. Client name links hover to --accent colour; non-hover state is --charcoal font-weight 700
7. Result badges: 10px tracked uppercase, --accent colour, 0.5px --accent border, padding 3px 8px
8. All six links resolve to existing routes — no 404s
9. Card grid section below the objectives now shows the label "Browse all client successes" (not "All projects")
10. Card grid itself is visually unchanged — same cards, same grid, same links
11. Reveal animations trigger as the objectives section scrolls into view
12. `npm run build` completes without errors
13. Typography audit: H2 is title case Archivo Condensed 700 (not all caps); objective H3s are title case; eyebrows and badges are ALL CAPS; hook text is sentence case
14. Colour audit: body text in --body (#2e2d2b), not --midgrey; --accent used on client name hover, result badges and left borders only
