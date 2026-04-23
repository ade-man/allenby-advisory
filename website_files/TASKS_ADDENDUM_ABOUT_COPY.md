# TASKS_ADDENDUM_ABOUT_COPY.md — About page copy amendment

This task updates the credential card on the About page. It can be completed at any point after Task 7 (About page) is verified.

---

## Task 7b — About page credential card: bio items update

**Goal:** Update the four bio list items in the right-hand credential card on the About page.

**File to edit:** `src/pages/about.astro`

---

### Change

In the credential card (right column of the hero section), replace the four bio list items as follows.

**Current:**
1. 10+ years in event technology and digital strategy
2. Projects across RX, Imbibe, Equiphotel and others
3. Speaker at EN Marketing Conference 2024
4. Contributor to Event Industry News, Collingwood Group

**Replace with:**
1. 10+ years in event technology and digital strategy
2. Projects across RX, Informa, Clarion events
3. Speaker at AEO, EN, Event Tech Live, IBTM events
4. Contributor to Event Industry News, Trade Show News Network

No other changes to the credential card. Name ("Ade Allenby"), title ("Founder, Allenby Advisory"), avatar ("AA"), and all styling remain unchanged.

---

### Verification

- The four bio items on `/about` match the updated copy above exactly
- No other content on the page has changed
- Styling is unchanged — each item retains the flex row, 4px accent dot, and 0.5px border-bottom between items
- `npm run build` completes without errors
