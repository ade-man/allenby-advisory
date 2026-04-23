# CONTENT_CLIENT_SUCCESSES_OBJECTIVES.md — Objectives section for Client Successes page

This file adds a new **"What are you trying to achieve?"** section to the existing Client Successes page (`src/pages/client-successes.astro`), sitting between the page header and the card grid.

It also relabels the existing card grid section from "All projects" to "Browse all client successes" so the grid reads as the full catalogue rather than competing with the objectives section for primary attention.

The two Equiphotel and Imbibe full case study deep-dives currently on the page are not addressed in this spec — they can be moved to their own pages in a later task if desired. For now they remain in place below the card grid.

---

## Page structure after this change

1. Page header (unchanged)
2. **What are you trying to achieve? — Case studies by objective** (NEW)
3. **Browse all client successes** (existing card grid, relabelled)
4. Equiphotel case study (existing — unchanged)
5. Imbibe case study (existing — unchanged)
6. Footer CTA (unchanged)

---

## New section: What are you trying to achieve?

**id:** objectives

Background: --white
Padding: var(--space-2xl) var(--space-lg)
Border-bottom: 0.5px solid --lightgrey

---

### Section header

**Eyebrow label (SectionLabel component):** Case studies by objective

**H2:** What are you trying to achieve?

Styling: Archivo Condensed 700, 34px, title case, --charcoal, line-height 1.1, margin-bottom 16px.

**Intro paragraph:** Most conversations start with a problem, not a project type. The work below is grouped by the kind of outcome event teams have come to us for — click through to the case study that's closest to your situation.

Styling: Archivo 400, 15px, line-height 1.7, --body, max-width 640px, margin-bottom 56px.

---

### Objectives list

**Layout:** Each objective is a full-width row, stacked vertically.
Grid per row: `grid-template-columns: 280px 1fr`, gap 48px.
Left column: eyebrow label + H3 (objective phrased as a short prompt).
Right column: 2–3 linked case study references, each as a row.
Between objectives: `border-bottom: 0.5px solid --lightgrey`. Last row: no border.
Row padding: 32px 0.

On mobile (max-width 768px): single column, left col stacks above right col, gap 20px, row padding 28px 0.

---

#### Row styling

**Left column:**
- Eyebrow (ALL CAPS, 11px, tracked 0.12em, --midgrey, font-family Archivo): e.g. "Objective 01"
- H3: Archivo Condensed 700, 22px, title case, --charcoal, line-height 1.2, margin-top 10px

**Right column (case study references):**
Each reference is a row within the right column. Layout: flex column, gap 18px between references.

Each reference contains:
- **Client name (link)**: Archivo 400, 15px, --charcoal, font-weight 700, text-decoration none. On hover: color --accent.
- **One-line hook**: Archivo 400, 14px, --body, line-height 1.5, display block, margin-top 2px.
- **Result badge (inline)**: Same styling as the CaseCard result badge — 10px, tracked, uppercase, --accent, 0.5px border --accent, padding 3px 8px, display inline-block, margin-top 8px.

---

### Content — five objectives

---

#### Objective 01

**Eyebrow:** Objective 01
**H3:** Launch or scale a digital product that drives revenue

**Case study references:**

1. **Incosmetics Global** — [link to `/client-successes/incosmetics-global`]
   - Hook: Scaled a niche feature-zone product show-wide into an NFC lead capture system — and created a new exhibitor revenue stream.
   - Result badge: 4× increase in paying exhibitors

2. **Clarion Events** — [link to `/client-successes/clarion-ai-assistant/`]
   - Hook: Deployed an AI matchmaking and concierge assistant across seven iterations — recognised with a leading industry innovation award.
   - Result badge: TSNN Best Innovation (B2C) 2025

---

#### Objective 02

**Eyebrow:** Objective 02
**H3:** Help visitors navigate a complex event

**Case study references:**

1. **Equiphotel Paris** — [link to `/client-successes#equiphotel`]
   - Hook: Turned persistent negative navigation feedback into a validated, multi-year improvement programme with evidence for ongoing investment.
   - Result badge: 100% growth in app adoption

---

#### Objective 03

**Eyebrow:** Objective 03
**H3:** Run structured business meetings inside a live event

**Case study references:**

1. **Imbibe Live London** — [link to `/client-successes#imbibe`]
   - Hook: Delivered a credible 1-2-1 meetings programme inside a show known for its convivial, socially-dominated atmosphere.
   - Result badge: Serious meetings. Party atmosphere.

---

#### Objective 04

**Eyebrow:** Objective 04
**H3:** Understand your audience through evidence, not assumption

**Case study references:**

1. **RX Global** — [link to `/client-successes/rx-global-research`]
   - Hook: Led a global research programme across ten countries that produced an award-winning framework for understanding attendee needs.
   - Result badge: 88% awareness amongst senior event managers

---

#### Objective 05

**Eyebrow:** Objective 05
**H3:** Unify fragmented systems and get your data working

**Case study references:**

1. **Global Banking Markets** — [link to `/client-successes/global-banking-markets/`]
   - Hook: Rebuilt the technology stack around HubSpot — replacing a fragmented set of spreadsheets, legacy CRM and disconnected tools with a unified, automated data platform.
   - Result badge: Single source of truth across every global event

---

### Animation notes

Apply `class="reveal"` to each objective row, so they stagger in as the visitor scrolls.

The section header (eyebrow, H2, intro paragraph) should appear immediately if it's above the fold on scroll-in, or use `class="reveal"` if below.

---

## Card grid section — relabel

The existing card grid section currently uses the label "All projects". Update this to **"Browse all client successes"**.

No other changes to the card grid itself. The cards remain in their current grid (3-column for six cards, or whatever the current live layout is — this spec does not change the grid structure).

Place a `border-top: 0.5px solid --lightgrey` above the relabelled section if it doesn't already have one, to visually separate it from the objectives section.

---

## CSS additions to `global.css`

Add under a comment `/* Objectives section — used on Client Successes page */`:

```css
.objectives-section {
  background: var(--white);
  padding: var(--space-2xl) var(--space-lg);
  border-bottom: 0.5px solid var(--lightgrey);
}

.objectives-intro {
  max-width: 640px;
  margin-bottom: 56px;
}

.objective-row {
  display: grid;
  grid-template-columns: 280px 1fr;
  gap: 48px;
  padding: 32px 0;
  border-bottom: 0.5px solid var(--lightgrey);
}

.objective-row:last-child {
  border-bottom: none;
}

.objective-row h3 {
  font-family: 'Archivo Condensed', sans-serif;
  font-weight: 700;
  font-size: 22px;
  color: var(--charcoal);
  line-height: 1.2;
  margin-top: 10px;
}

.objective-refs {
  display: flex;
  flex-direction: column;
  gap: 18px;
}

.objective-ref {
  display: block;
}

.objective-ref-client {
  font-family: 'Archivo', sans-serif;
  font-size: 15px;
  font-weight: 700;
  color: var(--charcoal);
  text-decoration: none;
  transition: color 0.2s ease;
}

.objective-ref-client:hover {
  color: var(--accent);
}

.objective-ref-hook {
  font-family: 'Archivo', sans-serif;
  font-size: 14px;
  color: var(--body);
  line-height: 1.5;
  margin-top: 2px;
}

.objective-ref-badge {
  display: inline-block;
  font-family: 'Archivo', sans-serif;
  font-size: 10px;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--accent);
  border: 0.5px solid var(--accent);
  padding: 3px 8px;
  margin-top: 8px;
}

@media (max-width: 768px) {
  .objective-row {
    grid-template-columns: 1fr;
    gap: 20px;
    padding: 28px 0;
  }
}
```

---

## Open items

- If a sixth objective is needed in future (e.g. "Choose the right technology platform"), the pattern extends cleanly — add another `.objective-row` block.

- Equiphotel and Imbibe are currently linked as anchors on the index page (`/client-successes#equiphotel` and `/client-successes#imbibe`). If those case studies are moved to their own pages in a future task, update the hrefs accordingly.
