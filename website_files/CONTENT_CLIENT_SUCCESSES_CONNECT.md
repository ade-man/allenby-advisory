# CONTENT_CLIENT_SUCCESSES_CONNECT.md — Connect (SABCO Group) Case Study

Page file: `src/pages/client-successes/connect.astro`
Active nav item: Client successes

This page follows the same structure as the GBM, Incosmetics Global and RX Global Research case studies. Read `CONTENT_CLIENT_SUCCESSES_GBM.md` first — Connect follows the GBM pattern closely (delivery partner credit in the meta card, same voice, same role-strip structure including the delivery partner attribution).

**Voice note:** This case study uses **first-person plural ("we")** for Allenby Advisory, mirroring the GBM pattern. Adam Price / The Growth Architect is credited as delivery partner.

**Delivery partner link:** Both occurrences of "The Growth Architect" on this page are linked to `https://www.thegrowtharchitect.co.uk/`, opening in a new tab with `rel="noopener noreferrer"`. This is consistent with the GBM page treatment: (1) the Delivery partner value in the meta card; (2) the "(The Growth Architect)" mention inline in the role strip paragraph.

**Source note:** Copy adapted from The Growth Architect's published case study, which Connect has signed off. Lifting the factual content and results directly avoids the need for further client sign-off before publication. Outcomes are framed as operational improvements rather than hard numeric metrics — the published source does not include quantified results.

---

## Updates required to existing pages

### 1. Add card to `src/pages/client-successes.astro` card grid

The card grid currently contains six cards in this order: Clarion, GBM, Incosmetics, RX Global, Equiphotel, Imbibe. Insert the Connect card **directly after GBM** — same objective category (systems and data consolidation), keeping that cluster of work together.

New order (seven cards):

1. Clarion Events
2. Global Banking Markets
3. **Connect (SABCO Group) — NEW**
4. Incosmetics Global
5. RX Global
6. Equiphotel Paris
7. Imbibe Live London

With seven cards in a 3-column grid, the third row will contain a single card on its own (2 rows of three + 1). That is acceptable — consistent with the interim state the site went through when GBM was the fifth card. No grid-template-columns change required.

**Card content:**
- Result badge: A commercial engine built for scale
- Title: Connect (SABCO Group) — Event sales operations
- Event tag: UAE · Conferences · B2B sponsorship
- Body: We designed and delivered a HubSpot-based commercial platform that turned fragmented tools and manual pricing into a structured, scalable sales operation.
- Link: Read the full story → href: "/client-successes/connect"

### 2. Add Connect to the "Case studies by objective" section on `client-successes.astro`

Connect belongs in **Objective 02: "Unify fragmented systems and get your data working"**, currently a single-reference objective containing only Global Banking Markets. Add Connect as the **second** case study reference in that objective row (below GBM), keeping GBM in the primary position as the more evidenced case study.

**Objective 02 — after update:**

1. **Global Banking Markets** — [link to `/client-successes/global-banking-markets/`] — *existing, unchanged*
   - Hook: Rebuilt the technology stack around HubSpot — replacing a fragmented set of spreadsheets, legacy CRM and disconnected tools with a unified, automated data platform.
   - Result badge: Single source of truth across every global event

2. **Connect (SABCO Group)** — [link to `/client-successes/connect`] — *NEW*
   - Hook: Designed a HubSpot-based commercial platform for a UAE event business — structured deal configuration, clean data architecture and a sales process built to scale.
   - Result badge: A commercial engine built for scale

No other objectives require changes. No CSS changes required — the new reference sits inside the existing `.objective-refs` flex column with the standard 18px gap between references.

---

## New page: `/client-successes/connect`

---

### Breadcrumb

← Client successes (href: "/client-successes")

Styling: font-size 11px, tracked, uppercase, --midgrey. Link: --accent, no underline.
Margin-bottom 18px above eyebrow.

---

### Page header

**Eyebrow label:** Case study — systems and data

**H1:** Connect (SABCO Group): event sales operations

**Body:** How we designed and delivered a scalable commercial platform for one of the UAE's leading event organisers — consolidating fragmented tools, introducing structured deal configuration, and building a sales operation fit for growth.

---

### Top section

**Layout:** 2-column — text left (1fr), meta card right (240px fixed)
Background: --white

Left column:
- **Label (ALL CAPS, --midgrey, 11px tracked):** The project in brief
- **H2:** From fragmented tools to a commercial engine built for scale
- **Body:** Connect's growth had outpaced its systems. Sales, event data and revenue tracking were spread across disconnected platforms, and the commercial model — built around tailored sponsorship packages — demanded more precision than manual processes could reliably support. We led an end-to-end tech stack review and rebuild, with HubSpot at the centre.
- **Button (primary):** Get in touch about a similar project → href: `https://calendar.app.google/kscewyXr9JDFXDYK8`, `external={true}`

Right column (meta card — --offwhite bg, 0.5px border):
- **Meta item 1** — Label: Client / Value: Connect (SABCO Group)
- **Meta item 2** — Label: Region / Value: United Arab Emirates
- **Meta item 3** — Label: Service type / Value: Project delivery · Retainer
- **Meta item 4** — Label: Delivery partner / Value: The Growth Architect
- **Metric box** (--charcoal bg):
  - Number: Scale
  - Description: Commercial engine built for growth

Note: Meta item 4 value "The Growth Architect" is a link to `https://www.thegrowtharchitect.co.uk/`, target `_blank`, `rel="noopener noreferrer"`. Matches the GBM page treatment.

---

### Body columns

**Layout:** 3-column grid using separator technique (--lightgrey parent, --white cells)

Column headers: ALL CAPS, 11px, tracked, --midgrey

**Column 1 — The challenge:**
Connect's existing setup relied on multiple disconnected tools. Event data was fragmented, revenue tracking was hard to pin down, and complex sponsorship packages required itemised configuration that manual pricing couldn't reliably deliver. The sales team needed a more structured way of working — across time zones and working practices spanning the UAE and the UK.

**Column 2 — What we did:**
Led a full tech stack review and commercial architecture rebuild with HubSpot as the central platform. Designed a custom data model reflecting how Connect's events are actually sold and delivered — with structured deal configuration, itemised packages, controlled discounting, and a migration from legacy systems into a clean, unified structure.

**Column 3 — The results:**
A centralised data model aligned to the commercial reality of the business. Accurate deal configuration even on complex packages. Improved revenue visibility through clear tracking of line items and discounts. Less manual effort, fewer pricing errors, stronger sales processes, and a platform built to scale with the business.

---

### Narrative section

Background: --offwhite
Padding: var(--space-2xl) var(--space-lg)

**H3:** The full story

Styling: Archivo Condensed 700, 22px, title case, --charcoal, margin-bottom 16px.

**Body paragraphs** (Archivo 400, 15px, --body, line-height 1.75, max-width 720px, margin-bottom 16px between paragraphs):

Para 1:
Connect, part of the SABCO Group, is a leading event organiser based in the United Arab Emirates, delivering high-profile conferences and industry events across the region. Their commercial model is built around tailored sponsorship packages and complex event offerings — a model that demands precision in both sales and data management, and one that had started to expose the limitations of the tooling underneath it.

Para 2:
The brief was clear but substantial. Data sat in multiple disconnected platforms with no unified structure. Complex event packages required itemised deal configuration that the existing setup couldn't support cleanly. Pricing and discounting were largely manual, increasing the risk of inconsistency. Visibility into sales performance and revenue breakdowns was limited. And the sales team itself was about to go through a significant shift — adopting more structured ways of working, delivered across different time zones and cultural working practices.

Para 3:
We led the engagement end-to-end, working with The Growth Architect as delivery partner on the HubSpot implementation. The approach was deliberate: rather than simply replacing one toolset with another, we designed a data architecture that reflected how Connect's events are actually sold and delivered — and built the commercial platform around that model.

Para 4:
Custom objects were designed and implemented to manage event data, with the relationships between events, packages and commercial activities clearly defined. Structured deal configuration enabled itemised event packages, with logic that allowed specific events to automatically trigger the relevant line items — ensuring accurate package representation, consistent pricing, and materially less manual input from the sales team. Controlled discounting mechanisms were introduced to improve governance without removing the flexibility the team needed in live negotiations.

Para 5:
Data migration was a significant part of the project. Consolidating records from multiple fragmented systems into a clean, unified structure in HubSpot wasn't a lift-and-shift exercise — it was a rebuild of how the business understands and uses its data, with clearer reporting, better segmentation, and improved long-term scalability as the direct outputs.

Para 6:
Given how substantial the shift was for the sales team, we focused heavily on user experience and adoption. Processes were designed to feel intuitive — reducing friction while introducing the structure needed to support growth. International delivery required careful coordination across time zones and sensitivity to working practices; the cadence of the project was structured to keep day-to-day disruption to a minimum.

Para 7:
The outcome is a commercial platform that operates with a level of clarity and control that wasn't previously possible. What was fragmented and manual is now structured, automated, and aligned with the way the business actually sells — a foundation Connect continues to build on through ongoing fractional delivery.

---

### Outcomes section

Background: --white
Padding: var(--space-2xl) var(--space-lg)

**H3:** Headline outcomes

Styling: Archivo Condensed 700, 22px, title case, --charcoal, margin-bottom 24px.

**Layout:** 3-column grid using separator technique (--lightgrey parent, --charcoal cells — dark metric boxes).

Each cell: bg --charcoal, padding 20px.
Number: Archivo Condensed 700, 32px, --white, display block, margin-bottom 6px.
Description: 11px, tracked, uppercase, #888780.

| Number | Description |
|---|---|
| Unified | Single structured data model |
| Consistent | Accurate deal and pricing configuration |
| Scalable | Foundation for future growth |

---

### Role strip

Background: --white
Padding: 24px 40px
Border-bottom: 0.5px solid --lightgrey

**Content:** [Role label] Tech stack review and strategy, HubSpot licensing negotiation, CRM data modelling and pipeline design, customer journey workshops, event app migration support, integration architecture, sales process redesign, team training and adoption support, and ongoing fractional delivery through a retainer model — working alongside delivery partner Adam Price (The Growth Architect), who led the HubSpot implementation and data migration.

Role label ("Allenby Advisory's role:"): 11px, tracked, uppercase, --charcoal, font-weight 700
Rest: 13px, --body

Note: This follows the GBM role strip pattern — the delivery partner credit sits inline at the end of the single role paragraph, not on a separate line below. The "(The Growth Architect)" mention is linked to `https://www.thegrowtharchitect.co.uk/` (target `_blank`, `rel="noopener noreferrer"`), matching the GBM page treatment. "Adam Price" is not linked.

---

### Footer CTA (dark section)

Background: --charcoal

**H2:** Working on something similar?

**Body:** Whether you're rethinking your tech stack, migrating to a new CRM, or building the commercial infrastructure to support a growing events business — we'd welcome the conversation.

**Button (light, external):** Book a free 30-minute call → href: `https://calendar.app.google/kscewyXr9JDFXDYK8`, `external={true}`

---

## Animation notes

Apply `class="reveal"` to:
- The top section (case-top)
- Each body column
- The narrative section
- The outcomes metrics row
- The role strip

The breadcrumb and page header should appear immediately (no reveal delay) as they are above the fold.

---

## Open decisions / flagged items

- **Metric framing:** The published source does not include quantified results (no percentages, no rebooking figures, no revenue uplift). The three outcome cells therefore use descriptive labels (Unified / Consistent / Scalable) rather than numbers, and the top-section metric box uses "Scale" as a descriptive anchor — consistent with the Clarion "2025" precedent for a non-numeric headline metric. If Connect subsequently shares hard numbers that can be published, the outcome cells and top-section metric box can be updated.
- **Delivery partner framing:** The Growth Architect is credited in the meta card ("Delivery partner") and inline at the end of the role strip. Both occurrences are linked to `https://www.thegrowtharchitect.co.uk/` (target `_blank`, `rel="noopener noreferrer"`). This exactly mirrors the GBM page treatment post-link-update.
- **Voice:** First-person plural ("we") throughout, per the voice rule for engagements delivered with a partner rather than personally recruited. Consistent with GBM.
