# TASKS_ADDENDUM.md — Incosmetics Global case study

This task should be completed after Task 6 (Client Successes page) is verified.

---

## Task 6b — Incosmetics Global case study page

**Goal:** Add the Incosmetics Global case study as a third client success, following the same pattern as Equiphotel and Imbibe.

**Read first:** `CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md` in full. Review `CONTENT_CLIENT_SUCCESSES.md` and the existing `client-successes.astro` to understand the layout patterns already in use.

**Steps:**

1. **Update the project index on `client-successes.astro`:**
   - Add a third CaseCard for Incosmetics Global using the card content in `CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md`
   - Update the case index grid to `grid-template-columns: repeat(3, 1fr)` to accommodate three cards

2. **Create `src/pages/client-successes/incosmetics-global.astro`:**

   Note: Astro file-based routing means the URL `/client-successes/incosmetics-global` requires the file to live at `src/pages/client-successes/incosmetics-global.astro`. You will need to create the `client-successes/` subdirectory under `pages/`.

3. **Build the page sections in order:**
   - Breadcrumb (← Client successes)
   - Page header (eyebrow, H1, body)
   - Top section (2-column: text + meta card with MetricBox)
   - Body columns (3-column separator grid: challenge / what we did / results)
   - Narrative section (--offwhite bg, H3 + 6 body paragraphs, max-width 720px)
   - Outcomes section (--white bg, H3 + 3 dark metric cells in separator grid)
   - Role strip
   - Footer CTA (dark section)

4. **Narrative section note:** This page has an additional "The full story" section not present on the Equiphotel or Imbibe pages. This is a full-width text section on --offwhite, using Archivo 400 15px --body, max-width 720px, with 16px margin between paragraphs. It sits between the 3-column body columns and the outcomes metrics.

5. **Outcomes section note:** The 3 metric cells in this section use the --charcoal background (same as MetricBox component) rather than --white. You can use three MetricBox components inside the separator grid, or replicate the styles inline.

6. **Add reveal animations** to all sections as specified in `CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md`.

7. **Update TASKS.md** — mark Task 6b as complete once verified.

**Verification:**
- `/client-successes` shows three cards in a 3-column grid
- `/client-successes/incosmetics-global` renders all sections correctly
- Breadcrumb link returns to `/client-successes`
- "Get in touch" button links to `/#contact`
- Metric cells show 4×, 90%+, New in Archivo Condensed 700 on charcoal bg
- Narrative paragraphs are in --body (#2e2d2b), max-width 720px, readable
- No console errors
