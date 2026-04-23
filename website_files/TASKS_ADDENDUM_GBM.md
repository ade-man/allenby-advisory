# TASKS_ADDENDUM_GBM.md — Global Banking Markets case study

This task should be completed after Task 6c (RX Global Customer Research case study page) is verified.

---

## Task 6d — Global Banking Markets case study page

**Goal:** Add the Global Banking Markets case study as a fifth client success, following the extended layout pattern already used for Incosmetics Global and RX Global Research.

**Read first:** `CONTENT_CLIENT_SUCCESSES_GBM.md` in full. Review `CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md` and `CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md` for the extended layout pattern (breadcrumb, narrative section, outcomes section). Review the existing `client-successes.astro` to understand the current project index grid.

**Important context:** This project was delivered in partnership with Adam Price (The Growth Architect), who led the HubSpot implementation. Ade's role was engagement lead and client relationship — the role strip credits the delivery partner explicitly, following the same pattern as the RX Global Research page credits The Sound HQ. The meta card also includes a "Delivery partner" item for the same reason. This is a deliberate content choice — do not edit or remove the partner attribution.

**Steps:**

1. **Update the project index on `client-successes.astro`:**
   - Add a fifth CaseCard for Global Banking Markets using the card content in `CONTENT_CLIENT_SUCCESSES_GBM.md`
   - Update the case index grid. The grid was set to `repeat(2, 1fr)` (2×2) in Task 6c. With a fifth card, switch to `grid-template-columns: repeat(3, 1fr)`. This will produce a 3-over-2 layout, with the fifth card sitting alone on the second row, left-aligned. That is acceptable — a future sixth case study will complete the layout.

2. **Create `src/pages/client-successes/global-banking-markets.astro`:**

   The `client-successes/` subdirectory under `pages/` should already exist from Task 6b. If not, create it.

3. **Build the page sections in order:**
   - Breadcrumb (← Client successes)
   - Page header (eyebrow, H1, body)
   - Top section (2-column: text + meta card with MetricBox)
   - Body columns (3-column separator grid: challenge / what we did / results)
   - Narrative section (--offwhite bg, H3 + 8 body paragraphs, max-width 720px)
   - Outcomes section (--white bg, H3 + 3 dark metric cells in separator grid)
   - Role strip
   - Footer CTA (dark section)

4. **No quote section.** Unlike the RX Global Research page, this case study does not include a pulled quote. The source material does not attribute a named quote, and we are not inventing one. The narrative section flows directly into the outcomes section.

5. **Narrative section note:** This page has 8 body paragraphs. Same styling as the other extended case studies: Archivo 400 15px --body, line-height 1.75, max-width 720px, 16px margin between paragraphs.

6. **Outcomes section note:** The 3 metric cells use --charcoal background (same as MetricBox component). Values are: 1 / 500+ / Live. The "1" metric has a longer description than usual ("Single source of truth across the business") — ensure the cell has enough padding and the description wraps cleanly without breaking the grid.

7. **Meta card note:** This case study has a fourth meta item (Delivery partner: The Growth Architect) in addition to the standard three. Follow the same pattern as Incosmetics (Technology) and RX Global (Agency).

8. **Role strip note:** The role strip on this page is longer than on other case studies because it explicitly credits Adam Price and The Growth Architect as the delivery partner. Render the full content as specified — do not shorten or rephrase.

9. **Booking links:** If Task 12 (Google Calendar booking integration) has already been completed, the "Get in touch about a similar project" button in the top section and the footer CTA button should both link to the Google Calendar booking URL with `external={true}`, matching the pattern used on the other case study pages. If Task 12 has not yet been completed, use `/#contact` as a placeholder — but update this file on this page when Task 12 runs.

10. **Add reveal animations** to all sections as specified in `CONTENT_CLIENT_SUCCESSES_GBM.md`.

**Verification:**
- `/client-successes` shows five cards, with the fifth sitting alone on a second row
- `/client-successes/global-banking-markets` renders all sections correctly
- Breadcrumb link returns to `/client-successes`
- "Get in touch" button links correctly (either `/#contact` or the Google Calendar URL depending on whether Task 12 has run)
- Meta card shows four items including "Delivery partner: The Growth Architect"
- Metric cells show 1, 500+, Live in Archivo Condensed 700 on charcoal bg
- Role strip explicitly credits Adam Price and The Growth Architect
- Narrative paragraphs are in --body (#2e2d2b), max-width 720px, readable
- No console errors
- No quote section is present on this page (intentional)
