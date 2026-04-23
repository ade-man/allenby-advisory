# TASKS_ADDENDUM_OBJECTIVES_REORDER.md — Reorder the objectives section

Small follow-up task to reorder the "What are you trying to achieve?" section on `/client-successes`. No content changes, no CSS changes — only the sequence in which the five objective rows appear on the page.

---

## Task 16 — Reorder the objectives section

**Goal:** Reorder the five `.objective-row` blocks on `/client-successes` so the sequence of objectives matches the strength-of-evidence ordering already applied to the card grid. The eyebrow labels are renumbered to match the new sequence.

**Read first:** The objectives section as currently built in `src/pages/client-successes.astro`.

---

### Why this change

The objectives section currently runs in the order it was drafted, which doesn't line up with the card grid order (Clarion → GBM → Incosmetics → RX → Equiphotel → Imbibe). Reordering the objectives brings the two sections into consistent visual logic — the first objective a visitor reads corresponds to the first kind of work they see in the card grid below.

The objective phrasing, case study links, hooks and result badges all stay exactly as they are. The only changes are:
1. The physical order of the five `.objective-row` blocks in the markup
2. The eyebrow number labels ("Objective 01", "Objective 02", etc.)

---

### New order

| New position | Eyebrow (new) | Objective | Case studies referenced |
|---|---|---|---|
| 1st row | Objective 01 | Launch or scale a digital product that drives revenue | Clarion, Incosmetics |
| 2nd row | Objective 02 | Unify fragmented systems and get your data working | Global Banking Markets |
| 3rd row | Objective 03 | Understand your audience through evidence, not assumption | RX Global |
| 4th row | Objective 04 | Help visitors navigate a complex event | Equiphotel Paris |
| 5th row | Objective 05 | Run structured business meetings inside a live event | Imbibe Live London |

---

### What changes vs. what doesn't

**What changes:**
- The order of the five `.objective-row` blocks in `src/pages/client-successes.astro`
- The eyebrow text on three rows (the GBM, RX, Equiphotel and Imbibe rows get new "Objective 0X" numbers)

**What does not change:**
- The H3 wording of any objective
- Case study links, hooks or result badges within each row
- Any CSS — the `.objective-row` styles, border rules and reveal animations all remain exactly as-is
- The section header (eyebrow "Case studies by objective", H2 "What are you trying to achieve?", intro paragraph)
- The card grid below the objectives section
- Any other section on the page

**Numbering rule:** Eyebrows are renumbered to reflect physical sequence, not preserved from the original draft. So the row that used to carry "Objective 05" (GBM) now carries "Objective 02". The row that used to carry "Objective 04" (RX) now carries "Objective 03". And so on. This keeps the sequence readable to a visitor — if they see "Objective 02" on the page, it means it's the second one down.

---

### Steps

1. Open `src/pages/client-successes.astro`
2. Locate the five `.objective-row` blocks inside the `.objectives-section`
3. Physically reorder the blocks in the markup to match the new sequence above
4. Update the eyebrow text inside each block so the numbers match the new position:
   - 1st row: "Objective 01" (unchanged)
   - 2nd row: "Objective 02" (was "Objective 05")
   - 3rd row: "Objective 03" (was "Objective 04")
   - 4th row: "Objective 04" (was "Objective 02")
   - 5th row: "Objective 05" (was "Objective 03")
5. Leave everything else inside each block untouched — the H3, the case study refs, the links, the hooks, the badges, the `class="reveal"`

---

### Verification

1. `/client-successes` loads without errors
2. The objectives section displays five rows in the new order: Clarion/Incosmetics → GBM → RX → Equiphotel → Imbibe
3. Eyebrow labels read "Objective 01" through "Objective 05" in sequence from top to bottom — every row's eyebrow matches its physical position
4. H3 wording on each row is unchanged from before
5. Case study links still resolve correctly (Clarion → `/client-successes/clarion-ai-assistant/`, GBM → `/client-successes/global-banking-markets/`, Incosmetics → `/client-successes/incosmetics-global`, RX → `/client-successes/rx-global-research`, Equiphotel → `/client-successes/equiphotel`, Imbibe → `/client-successes/imbibe`)
6. Result badges unchanged
7. Reveal animations trigger on scroll as before
8. Border rules between rows still applied correctly (0.5px --lightgrey bottom border on all rows except the last, which has none)
9. Card grid section below the objectives is unchanged
10. `npm run build` completes without errors
