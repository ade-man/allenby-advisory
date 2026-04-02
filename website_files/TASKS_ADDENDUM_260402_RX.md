# TASKS_ADDENDUM_RX.md — RX Global Customer Research case study

This task should be completed after Task 6b (Incosmetics Global case study page) is verified.

---

## Task 6c — RX Global Customer Research case study page

**Goal:** Add the RX Global Customer Research case study as a fourth client success, following the same pattern as Incosmetics Global (which includes the narrative and outcomes sections not present on the original Equiphotel and Imbibe pages).

**Read first:** `CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md` in full. Review `CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md` for the extended layout pattern (breadcrumb, narrative section, outcomes section, quote section). Review the existing `client-successes.astro` to understand the project index grid.

**Steps:**

1. **Update the project index on `client-successes.astro`:**
   - Add a fourth CaseCard for RX Global using the card content in `CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md`
   - Update the case index grid to accommodate four cards — switch to `grid-template-columns: repeat(2, 1fr)` (2×2 grid) or `repeat(4, 1fr)` depending on card width at the current breakpoint. A 2×2 layout is recommended to maintain readable card widths.

2. **Create `src/pages/client-successes/rx-global-research.astro`:**

   Note: The `client-successes/` subdirectory under `pages/` should already exist from Task 6b. If not, create it.

3. **Build the page sections in order:**
   - Breadcrumb (← Client successes)
   - Page header (eyebrow, H1, body)
   - Top section (2-column: text + meta card with MetricBox)
   - Body columns (3-column separator grid: challenge / what we did / results)
   - Narrative section (--offwhite bg, H3 + 7 body paragraphs, max-width 720px)
   - Quote section (--offwhite bg, Chet Burchett quote)
   - Outcomes section (--white bg, H3 + 3 dark metric cells in separator grid)
   - Role strip
   - Footer CTA (dark section)

4. **Narrative section note:** This page has 7 body paragraphs (one more than Incosmetics). Same styling: Archivo 400 15px --body, line-height 1.75, max-width 720px, 16px margin between paragraphs.

5. **Quote section note:** This page includes a quote from Chet Burchett (CEO, RX). It sits between the narrative and outcomes sections, on --offwhite background, using the same blockquote styling as the Sonja Van Praag quotes on the Equiphotel and Imbibe pages: Archivo 16px, italic, --charcoal, border-left 3px solid --accent, padding-left 20px, max-width 600px. Cite: 11px, tracked, uppercase, --midgrey, padding-left 23px.

6. **Outcomes section note:** The 3 metric cells use --charcoal background (same as MetricBox component). Values are: 88% / MRS / 19.

7. **Meta card note:** This case study has a fourth meta item (Agency: The Sound HQ) in addition to the standard three. Follow the same pattern as Incosmetics which also has a fourth item (Technology: NFC badge scanning).

8. **Add reveal animations** to all sections as specified in `CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md`.

**Verification:**
- `/client-successes` shows four cards in a 2×2 grid (or appropriate layout)
- `/client-successes/rx-global-research` renders all sections correctly
- Breadcrumb link returns to `/client-successes`
- "Get in touch" button links to `/#contact`
- Chet Burchett quote renders with accent left-border on --offwhite background
- Metric cells show 88%, MRS, 19 in Archivo Condensed 700 on charcoal bg
- Narrative paragraphs are in --body (#2e2d2b), max-width 720px, readable
- No console errors
