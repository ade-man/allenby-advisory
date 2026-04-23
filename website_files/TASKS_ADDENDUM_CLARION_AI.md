# TASKS_ADDENDUM_CLARION_AI.md — Clarion AI Assistant case study

This task can be completed at any point after Task 6c (RX Global Customer Research case study page) is verified. It adds a sixth client success case study following the same extended layout pattern as Incosmetics Global and RX Global Research, with three specific considerations: an embedded iterations table, third-person voice throughout the case study page, and a voice-neutral card summary on the index.

---

## Task 6e — Clarion AI Assistant case study page

**Goal:** Add the Clarion AI Assistant case study as a sixth client success, following the same pattern as Incosmetics Global and RX Global Research (the extended layout with breadcrumb, narrative, quote, outcomes sections). Reproduce the Clarion-signed narrative copy verbatim, including the seven-iteration table. Use third-person voice on the case study page. Use voice-neutral phrasing on the project index card.

**Read first:** `CONTENT_CLIENT_SUCCESSES_CLARION_AI.md` in full. Review `CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md` as the closest structural template. Review `TASKS_ADDENDUM_VOICE_AUDIT.md` for the voice rules that apply to this page. Review the existing `client-successes.astro` to understand the project index grid.

---

### Voice on this page

This case study follows the voice rules established in `TASKS_ADDENDUM_VOICE_AUDIT.md`:

- **Project index card summary** (on `client-successes.astro`) → voice-neutral, passive/subject phrasing. No "we", no "Ade".
- **Case study page itself** → third person throughout. Refers to the principal as "Ade", "Ade Allenby", or "he". Does not use "we" / "us" / "our".
- **Body column 2 header** → "What Ade did:" not "What we did:".
- **Footer CTA closer** → "Ade would welcome the conversation" not "we'd welcome the conversation".
- **Signed Clarion narrative and the TSNN quote** → preserved verbatim regardless of voice rules.

Do not "normalise" the third-person variants to match the pre-rewrite case study pattern — they are deliberate.

---

### Steps

1. **Update the project index on `client-successes.astro`:**
   - Add a sixth CaseCard for the Clarion AI Assistant using the card content in `CONTENT_CLIENT_SUCCESSES_CLARION_AI.md`.
   - The project index grid is already set to `grid-template-columns: repeat(3, 1fr)` (updated when the Connect case study was added as a fifth card) — **no grid change is required**. The sixth card fills the second row of the 3-column grid cleanly.
   - Card body uses the voice-neutral wording: "An AI matchmaking and concierge assistant was developed across seven iterations — deployed at live events in Europe and the US, and recognised with a leading industry innovation award."

2. **Create `src/pages/client-successes/clarion-ai-assistant.astro`:**

   The `client-successes/` subdirectory under `pages/` should already exist from earlier tasks.

3. **Build the page sections in order:**
   - Breadcrumb (← Client successes)
   - Page header (eyebrow, H1, body)
   - Top section (2-column: text + meta card with MetricBox — metric shows "2025" as the number and "TSNN Best Innovation on a B2C show" as the description)
   - Body columns (3-column separator grid: The challenge / What Ade did / The results)
   - Narrative section (--offwhite bg, H3 "The full story" + 3 signed paragraphs + iterations table + 3 more signed paragraphs, max-width 720px)
   - Quote section (--offwhite bg, TSNN award citation — note this is longer than other site quotes and uses US English)
   - Outcomes section (--white bg, H3 + 3 dark metric cells in separator grid)
   - Role strip
   - Footer CTA (dark section)

---

### Key implementation notes specific to this page

**A. Signed copy — preserve verbatim.**

The six narrative paragraphs and the TSNN quote are Clarion-signed copy. Reproduce them exactly as supplied in the content file — including:

- UK-English spelling in the signed narrative ("fully-fledged", "amongst", "customisation") — do not normalise to US
- US-English spelling in the TSNN quote ("optimized", "personalizing", "organizers") — do not anglicise
- Factual details including technology names (Langflow, DataStax, N8N, OpenAI Azure, Anthropic, Grok) and iteration dates
- The specific phrase "Clarion's partnership with Allenby Advisory and Visual Hive" in Para 4 — this is Clarion's chosen framing of the relationship

If any typographic or grammatical issue seems present in the signed copy, flag it to Ade before altering — do not silently correct.

**B. Iterations table.**

A new visual element on this page: a seven-row HTML table summarising the iterations. This does not appear on any other case study page. Follow the styling spec in the content file:

- Header row: --offwhite bg, ALL CAPS 10px tracked --midgrey, font-weight 700
- Body rows: --white bg, 13px --body, 0.5px --lightgrey border-bottom per row
- Column widths: 56px (Iteration) / ~220px (Event) / 1fr (Test outcomes)
- Iteration numbers: Archivo Condensed 700, 16px, --charcoal, centered
- Event names: 13px, --charcoal, font-weight 700
- Test outcomes: 13px, --body, one outcome per line with 4px gap between

On mobile (≤768px), the table should scroll horizontally inside its container (`overflow-x: auto`) rather than restructure. Add a subtle visual affordance (a gentle right-edge fade or a small "scroll →" hint) only if the table appears cut off without it — otherwise leave clean.

Table lives inside the 720px narrative column, with margin 24px 0 32px, visually bridging Para 3 and Para 4 of the signed copy.

**C. Partner framing — Visual Hive.**

Visual Hive were engaged by Clarion directly, selected on Ade's recommendation, reporting into Ade on delivery. This is **different** from the RX Global / Sound HQ model where The Sound HQ were recruited and managed as part of Ade's engagement.

Treatment across the page:
- Meta card label: **"Delivery partner"** (not "Partner" as used for RX Global's "Agency: The Sound HQ")
- Role strip: explicitly uses "selection and recommendation of Visual Hive as delivery partner" and "Bogdan Maran's team at Visual Hive reporting into Ade on delivery"
- Narrative: preserved verbatim from signed copy — "under Ade's guidance, Clarion partnered with Bogdan Maran and his team at Visual Hive"
- Intro body (top section) and body column 2: third-person framing — "On Ade's guidance, Clarion engaged Visual Hive…" and "identifying Visual Hive as the right delivery partner. Clarion engaged Visual Hive directly on Ade's recommendation…"

Do not replace any of this with shortcut phrasing like "we partnered with Visual Hive" or "Ade's delivery team at Visual Hive" — both misrepresent the commercial structure.

**D. Metric box — non-numeric headline.**

The headline metric on this case study is an award year ("2025") rather than a percentage or multiplier. This is a visual outlier compared to Incosmetics (4×), RX Global (88%) and others — but the description line carries the substance ("TSNN Best Innovation on a B2C show"). Do not "fix" this by switching to a numeric metric. If "2025" looks visually thin at 36px next to the longer description, drop the number to 32px (matching the outcomes cells) rather than resizing the box.

**E. Quote length.**

The TSNN quote is longer than the 30–40-word quotes used elsewhere on the site. Blockquote max-width widens to 620px (from the 600px used on other pages) to accommodate without line-lengths becoming cramped. Do not trim the quote to match other pages — the full citation is the signed award text.

**F. Outcomes section.**

Three dark metric cells using the same pattern as Incosmetics and RX Global. Values: 7 / 57%+ / 77%. These are numeric and consistent with the other case study outcomes strips.

---

### Add reveal animations

Apply `class="reveal"` per the animation notes in the content file. The iterations table reveals as part of the narrative section (one reveal for the whole narrative block, not a separate reveal for the table).

---

### Verification

1. `/client-successes` shows six cards in a 3-column grid (two rows of three)
2. The Clarion card body on `/client-successes` reads voice-neutral: **"An AI matchmaking and concierge assistant was developed across seven iterations…"** — not "Ade led the product development…" and not "We led the product development…"
3. `/client-successes/clarion-ai-assistant` renders all sections correctly
4. Breadcrumb link returns to `/client-successes`
5. "Get in touch about a similar project" button links to `/#contact`
6. Meta card shows four items (Client / Scope / Service type / **Delivery partner**) plus the MetricBox showing "2025 — TSNN Best Innovation on a B2C show"
7. Body column 2 header reads **"What Ade did"** — not "What we did"
8. Six narrative paragraphs render in order, verbatim to the signed copy, with the iterations table sitting between Para 3 and Para 4
9. Iterations table renders with seven rows, correct column widths, --offwhite header, --white body rows, 0.5px --lightgrey row separators
10. On mobile (≤768px), the iterations table scrolls horizontally without breaking the page layout; the narrative paragraphs stack normally
11. TSNN quote renders in full (not trimmed), with accent left-border on --offwhite background, attributed to "Trade Show News Network — Best Innovation on a B2C show, 2025"; US-English spelling preserved
12. Outcomes cells show 7, 57%+, 77% in Archivo Condensed 700 on charcoal bg
13. Role strip explicitly credits "selection and recommendation of Visual Hive as delivery partner" and "Bogdan Maran's team at Visual Hive reporting into Ade on delivery"
14. Footer CTA body reads **"Ade would welcome the conversation"** — not "we'd welcome the conversation"
15. Narrative paragraphs are in --body (#2e2d2b), max-width 720px, readable
16. Footer CTA "Book a free 30-minute call" button opens Google Calendar booking link in a new tab
17. No console errors
18. `npm run build` completes without errors
