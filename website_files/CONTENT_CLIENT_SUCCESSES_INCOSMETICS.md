# CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md — Incosmetics Global Case Study

Page file: `src/pages/client-successes/incosmetics-global.astro`
Active nav item: Client successes

This page follows the same structure as the Equiphotel and Imbibe case studies in `CONTENT_CLIENT_SUCCESSES.md`. Read that file first to understand the layout patterns. Also add this case study as a third card in the project index on `client-successes.astro`.

---

## Updates required to existing pages

### 1. Add card to `src/pages/client-successes.astro` project index

Add a third CaseCard to the project index grid. Update the grid from `grid-template-columns: 1fr 1fr` to `grid-template-columns: repeat(3, 1fr)` to accommodate three cards.

**Card 3:**
- Result badge: 4× increase in paying exhibitors
- Title: Incosmetics Global — Lead capture strategy
- Event tag: Paris / Barcelona · Cosmetics ingredients · Trade show
- Body: A niche feature-zone product was scaled show-wide into an NFC lead capture system — and turned into a new exhibitor revenue stream.
- Link: Read the full story → href: "/client-successes/incosmetics-global"

---

## New page: `/client-successes/incosmetics-global`

---

### Breadcrumb

← Client successes (href: "/client-successes")

Styling: font-size 11px, tracked, uppercase, --midgrey. Link: --accent, no underline.
Add margin-bottom 18px above eyebrow.

---

### Page header

**Eyebrow label:** Case study — project delivery

**H1:** Incosmetics Global: lead capture strategy

**Body:** How a new NFC-based content capture technology multiplied leads and created a new exhibitor revenue stream at one of Europe's leading cosmetics ingredients events.

---

### Top section

**Layout:** 2-column — text left (1fr), meta card right (240px fixed)
Background: --white

Left column:
- **Label (ALL CAPS, --midgrey, 11px tracked):** The project in brief
- **H2:** From feature-zone experiment to show-wide digital lead capture
- **Body:** The event had an existing self-scan product limited to feature zones. Ade identified an opportunity to scale it show-wide using NFC badging technology — turning a niche feature into a commercially significant, opt-out exhibitor product.
- **Button (primary):** Get in touch about a similar project → href: "/#contact"

Right column (meta card — --offwhite bg, 0.5px border):
- **Meta item 1** — Label: Event / Value: Incosmetics Global
- **Meta item 2** — Label: Locations / Value: Paris / Barcelona (alternating)
- **Meta item 3** — Label: Service type / Value: Project delivery
- **Meta item 4** — Label: Technology / Value: NFC badge scanning
- **Metric box** (--charcoal bg):
  - Number: 4×
  - Description: Increase in paying exhibitors

---

### Body columns

**Layout:** 3-column grid using separator technique (--lightgrey parent, --white cells)

Column headers: ALL CAPS, 11px, tracked, --midgrey

**Column 1 — The challenge:**
The event had a content capture solution limited to feature zones. The brief was to review the existing strategy and implement a show-wide approach that would scale — increasing both exhibitor and visitor engagement with digital lead capture.

**Column 2 — What Ade did:**
Devised a value proposition and technology implementation strategy around NFC badging devices. When a visitor taps the device, their badge ID is captured — triggering an automatic daily "trip report" of everything they collected, with no manual data work required for exhibitors.

**Column 3 — The results:**
Leads captured multiplied significantly. The proportion of exhibitors paying for the product increased fourfold — to over 90% — in the year following the initial trial. A new exhibitor revenue stream was created from a product previously offered for free.

---

### Narrative section

Background: --offwhite
Padding: var(--space-2xl) var(--space-lg)

**H3:** The full story

Styling: Archivo Condensed 700, 22px, title case, --charcoal, margin-bottom 16px.

**Body paragraphs** (Archivo 400, 15px, --body, line-height 1.75, max-width 720px, margin-bottom 16px between paragraphs):

Para 1:
Incosmetics Global is the premier trade event for cosmetics ingredients, alternating between Paris and Barcelona. Exhibitors use it to demonstrate new innovations and discuss supply for the coming year — a commercially high-stakes environment where lead quality and follow-up matter significantly.

Para 2:
The event already had a self-scan product attached to its feature zones — curated showcase areas designed to drive exhibitor footfall. Small badge-scanning devices allowed visitors to self-scan and receive content post-event. The opportunity was to take that concept and scale it across the entire show floor using a more capable technology.

Para 3:
Working with the Global Innovation Team and the UK Digital Team, Ade trialled NFC-enabled devices that allow visitors to tap their badge at any exhibitor stand. The tap triggers a capture — no action required from the exhibitor — and at the end of each day, visitors receive an automatic "trip report" containing everything they collected: company descriptions, product information, brochures and contact details.

Para 4:
The implementation required simultaneous process changes across several areas: an NFC pairing step added to badge collection, an exhibitor onboarding communications programme (pre-event and onsite), and clear onsite guidance for exhibitors on device placement for best results.

Para 5:
Critically, the value proposition was reframed. Rather than being sold as a paid-for lead retrieval add-on, the product was redesigned as an opt-out feature — built on the idea of enabling visitors to collect digital content from anywhere at the event without carrying paper brochures. The product was offered free of charge in year one to prove value, then introduced as a standard contract item in subsequent years.

Para 6:
The Global Innovation Team collaborated closely with the vendor to analyse the rich dataset generated from the show floor — delivering exhibitor-facing insights that reinforced the product's value and gave sales and marketing teams new intelligence about how visitors engaged with the event.

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
| 4× | Increase in paying exhibitors |
| 90%+ | Exhibitor uptake in year two |
| New | Revenue stream created |

---

### Role strip

Background: --white
Padding: 24px 40px
Border-bottom: 0.5px solid --lightgrey

**Content:** [Role label] Product strategy, implementation strategy, customer communication strategy, metrics and reporting, and supporting the team through end-to-end delivery.

Role label ("Ade's role:"): 11px, tracked, uppercase, --charcoal, font-weight 700
Rest: 13px, --body

---

### Footer CTA (dark section)

Background: --charcoal

**H2:** Working on something similar?

**Body:** Whether you're looking to improve exhibitor lead capture, launch a digital content strategy, or scale an existing product — Ade would welcome the conversation.

**Button (light):** Book a free 30-minute call → href: "/#contact"

---

## Animation notes

Apply `class="reveal"` to:
- The top section (case-top)
- Each body column
- The narrative section
- The outcomes metrics row
- The role strip

The breadcrumb and page header should appear immediately (no reveal delay) as they are above the fold.
