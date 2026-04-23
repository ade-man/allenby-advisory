# TASKS_ADDENDUM_PORTFOLIO.md — Portfolio restructure (Equiphotel + Imbibe pages, reorder, objectives update)

This task should be completed after Task 14 (objectives section) is built and verified. It makes three related changes to the Client Successes page in a single coordinated edit, so the portfolio is consistently structured when the task ends.

---

## Task 15 — Portfolio restructure

**Goal:** Move the Equiphotel and Imbibe case studies onto their own pages (matching the Incosmetics/RX/Clarion/GBM pattern), reorder the card grid and objectives section by strength of evidence, and strip the inline case studies off the Client Successes index page.

**Read first:**
- `CONTENT_CLIENT_SUCCESSES_EQUIPHOTEL.md` in full
- `CONTENT_CLIENT_SUCCESSES_IMBIBE.md` in full
- Review `CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md` and `CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md` for the shared case study layout pattern
- The current `src/pages/client-successes.astro` to understand what's being removed

---

### Why these three changes belong together

The card grid order, the objectives section links, and the existence of the inline Equiphotel/Imbibe sections all reference each other. Changing any one of them independently leaves the page in an inconsistent state — for example, reordering the cards without moving Equiphotel/Imbibe to their own pages creates a visual ordering that puts older, weaker-evidence work directly below newer work, while the inline case studies still exist below and pull attention back to them. Doing all three at once keeps the page coherent at every stage of the edit.

---

### Change 1 — Build Equiphotel case study page

Create `src/pages/client-successes/equiphotel.astro` following `CONTENT_CLIENT_SUCCESSES_EQUIPHOTEL.md` exactly.

This page uses the **full extended template** (breadcrumb, header, top section with meta card, 3-col body, narrative, outcomes, role strip, footer CTA) — same as Incosmetics and RX.

Key notes:

- No pull quote on this page. The Sonja Van Praag quote that previously sat under the inline Equiphotel section was about Imbibe (references "Imbibe Live audience") — it moves to the Imbibe page, not here.
- Outcomes section has three cells: **100%** / **100,000 sqm** / **Evidence-led**. The third cell is a descriptive anchor rather than a number — consistent with the "New" cell on Incosmetics and the "MRS" cell on RX. Archivo Condensed 700 at 32px handles the hyphenated compound word; it may sit on two lines in the cell depending on viewport, which is acceptable.
- Meta card has four items rather than three — the fourth is "Research partner: Global Research".

---

### Change 2 — Build Imbibe case study page

Create `src/pages/client-successes/imbibe.astro` following `CONTENT_CLIENT_SUCCESSES_IMBIBE.md` exactly.

This page uses a **shortened variant** of the extended template: it has no outcomes metrics section. The page flow is:

1. Breadcrumb
2. Page header
3. Top section (with meta card)
4. Body columns (3-col)
5. Narrative section
6. Quote section
7. Role strip
8. Footer CTA

The quote section sits where the outcomes section would normally be. This is intentional — no outcome metrics were captured for this project, and the page is honest about that rather than filling the strip with descriptive anchors. Do not add an outcomes section "for consistency".

Key notes:

- The Sonja Van Praag quote lives here. It's the same quote currently showing under the inline Equiphotel section on the index page.
- The meta card's metric box uses "1-2-1" as a descriptive anchor rather than a number — consistent with the descriptive-cell pattern elsewhere.
- Meta card has four items rather than three — the fourth is "Context: Post-acquisition integration".

---

### Change 3 — Strip inline Equiphotel and Imbibe sections from the index page

On `src/pages/client-successes.astro`, delete **everything** from the end of the card grid section down to the start of the footer CTA. Specifically, remove:

- The inline Equiphotel case study block (top section, body columns, quote section, role strip)
- The inline Imbibe case study block (top section, body columns, quote section, role strip)

The index page flow after this change becomes:

1. Page header
2. **What are you trying to achieve?** (objectives section — from Task 14)
3. **Browse all client successes** (card grid, relabelled in Task 14)
4. Footer CTA

No inline case studies remain on the index page. Every case study is now reached via its own route under `/client-successes/[slug]`.

---

### Change 4 — Reorder the card grid

The card grid currently reflects build order. Reorder to the following sequence (strongest/most recent first):

1. **Clarion Events** — AI assistant product development
2. **Global Banking Markets** — HubSpot as the central data platform
3. **Incosmetics Global** — Lead capture strategy
4. **RX Global** — Attendee behavioural archetypes
5. **Equiphotel Paris** — Visitor navigation
6. **Imbibe Live London** — 1-2-1 meetings

Six cards in total. All cards retain their existing copy, result badges and links. Update the `href` on the Equiphotel and Imbibe cards from the anchor links (`#equiphotel`, `#imbibe`) to the new routes (`/client-successes/equiphotel`, `/client-successes/imbibe`).

With six cards, a 3-column grid produces two rows of three — clean layout. If the current live grid is 3-column, leave it as 3-column. If it's any other layout, stay consistent with what's live.

---

### Change 5 — Reorder within the objectives section

In the objectives section built in Task 14, Objective 01 ("Launch or scale a digital product that drives revenue") currently lists Incosmetics before Clarion. Swap the order so Clarion comes first:

**Objective 01 — after reorder:**

1. **Clarion Events** — [link to `/client-successes/clarion-ai-assistant/`]
   - Hook: Deployed an AI matchmaking and concierge assistant across seven iterations — recognised with a leading industry innovation award.
   - Result badge: TSNN Best Innovation (B2C) 2025

2. **Incosmetics Global** — [link to `/client-successes/incosmetics-global`]
   - Hook: Scaled a niche feature-zone product show-wide into an NFC lead capture system — and created a new exhibitor revenue stream.
   - Result badge: 4× increase in paying exhibitors

No other objectives require reordering.

Also update the hrefs on:
- **Equiphotel Paris** (Objective 02) — from `/client-successes#equiphotel` to `/client-successes/equiphotel`
- **Imbibe Live London** (Objective 03) — from `/client-successes#imbibe` to `/client-successes/imbibe`

---

### Verification

**New case study pages:**

1. `/client-successes/equiphotel` renders all sections: breadcrumb, page header, top section (with 4-item meta card and 100% metric), 3-column body, narrative, outcomes (100% / 100,000 sqm / Evidence-led), role strip, footer CTA
2. `/client-successes/imbibe` renders all sections: breadcrumb, page header, top section (with 4-item meta card and "1-2-1" metric), 3-column body, narrative, quote (Sonja Van Praag), role strip, footer CTA
3. Imbibe page does **not** have an outcomes section — this is correct, not a bug
4. Equiphotel page does **not** have a quote section — this is correct, not a bug
5. Breadcrumb on both pages links back to `/client-successes`
6. "Get in touch" buttons on both pages open the Google Calendar booking URL in a new tab
7. Footer CTA buttons on both pages open the booking URL in a new tab

**Index page (`/client-successes`):**

8. Page flow is: page header → objectives section → card grid → footer CTA. No inline Equiphotel or Imbibe sections remain anywhere on this page
9. Card grid shows six cards in the new order: Clarion, GBM, Incosmetics, RX, Equiphotel, Imbibe
10. Card grid label reads "Browse all client successes" (unchanged from Task 14)
11. Equiphotel card href is `/client-successes/equiphotel` (not `#equiphotel`)
12. Imbibe card href is `/client-successes/imbibe` (not `#imbibe`)
13. All six cards link to live, routable pages — no 404s

**Objectives section:**

14. Objective 01 lists Clarion first, Incosmetics second
15. Equiphotel (Objective 02) links to `/client-successes/equiphotel`
16. Imbibe (Objective 03) links to `/client-successes/imbibe`
17. All other objective links unchanged

**Other pages — check for broken internal links:**

18. Search the full site for any remaining anchors to `#equiphotel` or `#imbibe` and update them to the new routes. Likely candidates: the homepage "Recent work" case cards, any cross-references in other case study pages, the sitemap if present
19. Specifically: on `src/pages/index.astro`, the "Recent work" case cards currently link to `/client-successes#equiphotel` and `/client-successes#imbibe` — update these to `/client-successes/equiphotel` and `/client-successes/imbibe`

**General:**

20. `npm run build` completes without errors
21. Typography audit on both new pages: page H1 title case Archivo Condensed 700; H2s title case; eyebrows and badges ALL CAPS; body text in --body (#2e2d2b); narrative paragraphs max-width 720px
22. Reveal animations trigger on both new pages as the user scrolls
23. Mobile layout (≤768px) on both new pages: meta card stacks below top section text; 3-column body stacks to single column; narrative paragraphs fit viewport without horizontal overflow
