# TASKS_ADDENDUM_CONNECT.md — Connect (SABCO Group) case study

This task can be completed at any point after the Clarion AI, GBM, Objectives, and Objectives Reorder addendums have all been applied. It adds a seventh case study to the site and updates the card grid and objectives section to include it.

---

## Task 6f — Connect (SABCO Group) case study page

**Goal:** Add the Connect (SABCO Group) case study as a seventh client success, following the GBM pattern (first-person plural voice; delivery partner credited in the meta card and inline in the role strip, with both occurrences of "The Growth Architect" linked to `https://www.thegrowtharchitect.co.uk/`). Also update the card grid and the objectives section on the index page to include Connect.

**Read first:**
- `CONTENT_CLIENT_SUCCESSES_CONNECT.md` in full
- `CONTENT_CLIENT_SUCCESSES_GBM.md` and `TASKS_ADDENDUM_GBM.md` — Connect follows this pattern most closely (delivery partner credit, voice, role strip structure)
- The current state of `src/pages/client-successes.astro` — card grid order and objectives section as they stand after `TASKS_ADDENDUM_PORTFOLIO.md` and `TASKS_ADDENDUM_OBJECTIVES_REORDER.md` have been applied

**Steps:**

### 1. Update the card grid on `src/pages/client-successes.astro`

Insert a new CaseCard for Connect directly after the Global Banking Markets card. The grid order becomes seven cards:

1. Clarion Events
2. Global Banking Markets
3. **Connect (SABCO Group) — NEW, insert here**
4. Incosmetics Global
5. RX Global
6. Equiphotel Paris
7. Imbibe Live London

With seven cards in a 3-column grid, the last row contains a single card on its own (2 rows of three + 1 orphan). This is acceptable — it matches the interim state the site previously went through when GBM was the fifth card. Do not change the grid-template-columns.

Use the card content specified in `CONTENT_CLIENT_SUCCESSES_CONNECT.md`.

### 2. Update the objectives section on `src/pages/client-successes.astro`

Locate the `.objective-row` block for **Objective 02 ("Unify fragmented systems and get your data working")** — this currently contains a single `.objective-ref` block for Global Banking Markets.

Add a second `.objective-ref` block directly below the GBM reference, for Connect. The GBM reference stays first (it is the more evidenced case study); Connect sits second.

Use the reference content specified in `CONTENT_CLIENT_SUCCESSES_CONNECT.md` section 2 — client name, hook, and result badge.

No CSS changes required. The new reference sits inside the existing `.objective-refs` flex column with the standard 18px gap between references. The `.objective-row` styling, eyebrow number ("Objective 02"), H3 ("Unify fragmented systems and get your data working") and all other objectives remain unchanged.

### 3. Create `src/pages/client-successes/connect.astro`

The `client-successes/` subdirectory under `pages/` already exists.

### 4. Build the page sections in order

- Breadcrumb (← Client successes)
- Page header (eyebrow, H1, body)
- Top section (2-column: text + meta card with MetricBox)
- Body columns (3-column separator grid: challenge / what we did / results)
- Narrative section (--offwhite bg, H3 + 7 body paragraphs, max-width 720px)
- Outcomes section (--white bg, H3 + 3 dark metric cells in separator grid)
- Role strip
- Footer CTA (dark section)

### 5. Meta card notes

This case study uses the four-meta-item pattern (Client / Region / Service type / Delivery partner), matching the GBM, Incosmetics and RX Global pages.

The "Delivery partner: The Growth Architect" meta item value is **linked** to `https://www.thegrowtharchitect.co.uk/`, opening in a new tab with `rel="noopener noreferrer"`. This matches the GBM page post-link-update. Reference the existing GBM implementation for the exact markup pattern.

### 6. Metric box note

The top-section metric box uses a text label ("Scale") rather than a number. This is deliberate — the published source does not include quantified outcomes. The MetricBox component handles string values in the number slot (this pattern was already established by the Clarion page using "2025" as its headline metric).

### 7. Outcomes section note

The 3 outcome cells use descriptive labels (Unified / Consistent / Scalable) rather than numbers, for the same reason as the top-section metric box. Styling is identical to other case studies — Archivo Condensed 700 on --charcoal background.

### 8. Role strip notes

This page uses the **GBM-style role strip** — a single inline paragraph where the delivery partner credit sits at the end of the role content, not on a separate line below.

Inside that paragraph, the "(The Growth Architect)" mention is **linked** to `https://www.thegrowtharchitect.co.uk/`, opening in a new tab with `rel="noopener noreferrer"`. "Adam Price" is not linked. This matches the GBM page post-link-update — reference the existing GBM role strip implementation for the exact markup.

### 9. Voice

First-person plural ("we") throughout — consistent with the GBM case study. Do not convert to third-person ("Ade") on this page.

### 10. Booking links

Both the "Get in touch about a similar project" button in the top section and the footer CTA button link to the Google Calendar booking URL (`https://calendar.app.google/kscewyXr9JDFXDYK8`) with `external={true}`, matching the pattern used on all other case study pages post-Task 12.

### 11. Add reveal animations

Apply reveal animations to all sections as specified in `CONTENT_CLIENT_SUCCESSES_CONNECT.md`.

---

## Verification

**New case study page (`/client-successes/connect`):**

1. Page renders all sections correctly in the specified order
2. Breadcrumb link returns to `/client-successes`
3. "Get in touch" button opens Google Calendar booking page in a new tab
4. Meta card shows four items including "Delivery partner: The Growth Architect" — the value is a link to `https://www.thegrowtharchitect.co.uk/` opening in a new tab with `rel="noopener noreferrer"`
5. Top-section metric box shows "Scale" with descriptive text below ("Commercial engine built for growth")
6. Outcome cells show Unified / Consistent / Scalable on --charcoal background
7. Role strip renders as a single inline paragraph with the delivery partner credit at the end — "(The Growth Architect)" is a link to `https://www.thegrowtharchitect.co.uk/` opening in a new tab with `rel="noopener noreferrer"`; "Adam Price" is not linked
8. Narrative uses "we" throughout (not "Ade")
9. Narrative paragraphs are in --body (#2e2d2b), max-width 720px, readable
10. Footer CTA "Book a free 30-minute call" button opens Google Calendar booking page in a new tab

**Card grid on `/client-successes`:**

11. Seven cards in total, in the order: Clarion, GBM, **Connect**, Incosmetics, RX, Equiphotel, Imbibe
12. Connect card sits directly after GBM
13. 3-column grid, with the seventh card sitting alone on the third row — this is acceptable
14. Connect card text, badge and href match the spec
15. All other cards unchanged

**Objectives section on `/client-successes`:**

16. Objective 02 ("Unify fragmented systems and get your data working") now shows two case study references
17. GBM reference remains first, unchanged
18. Connect reference sits second, with correct hook and result badge
19. Eyebrow remains "Objective 02" — no renumbering required
20. All other objective rows unchanged

**General:**

21. No console errors
22. `npm run build` completes without errors
23. Reveal animations trigger on scroll on the new case study page and on the updated objectives section
24. Mobile layout (≤768px) on the new page: meta card stacks below top section text; 3-column body stacks to single column; narrative paragraphs fit viewport without horizontal overflow
