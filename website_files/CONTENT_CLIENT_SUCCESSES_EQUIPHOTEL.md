# CONTENT_CLIENT_SUCCESSES_EQUIPHOTEL.md — Equiphotel Paris Case Study

Page file: `src/pages/client-successes/equiphotel.astro`
Active nav item: Client successes

This page follows the same structure as the Incosmetics Global and RX Global Research case studies — the extended template with breadcrumb, narrative section and outcomes section. Read `CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md` and `CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md` first for the layout patterns.

**Note on this case study:** Equiphotel and Imbibe currently live as inline sections on the Client Successes index page (`/client-successes`). This page moves Equiphotel onto its own route so every case study is treated consistently. The inline Equiphotel section on the index page is being removed as part of the same task.

**Note on the pull quote:** This page does **not** include a pull quote section. The Sonja Van Praag quote that currently sits under the inline Equiphotel section on the index page is actually about Imbibe (it references "Imbibe Live audience") — it was misplaced in the original build. It moves to the Imbibe page and should not appear here.

---

## Page

---

### Breadcrumb

← Client successes (href: "/client-successes")

Styling: font-size 11px, tracked, uppercase, --midgrey. Link: --accent, no underline. Margin-bottom 18px above eyebrow.

---

### Page header

**Eyebrow label:** Case study — project delivery

**H1:** Equiphotel Paris: visitor navigation strategy

**Body:** How we turned one of the event's most persistent pain points — navigation across a 100,000 sqm venue — into a measurable, multi-year improvement programme backed by onsite visitor research.

---

### Top section

**Layout:** 2-column — text left (1fr), meta card right (240px fixed)
Background: --white

Left column:
- **Label (ALL CAPS, --midgrey, 11px tracked):** The project in brief
- **H2:** From recurring complaint to evidence-led investment
- **Body:** Post-event surveys had flagged navigation as a top source of visitor dissatisfaction for several years running. With the signage budget under pressure, we developed a digital-first strategy supported by onsite research — producing both immediate improvements and a multi-year roadmap informed by visitor evidence.
- **Button (primary, external):** Get in touch about a similar project → href: `https://calendar.app.google/kscewyXr9JDFXDYK8`, `external={true}`

Right column (meta card — --offwhite bg, 0.5px border):
- **Meta item 1** — Label: Event / Value: Equiphotel Paris
- **Meta item 2** — Label: Venue / Value: Porte de Versailles
- **Meta item 3** — Label: Service type / Value: Project delivery
- **Meta item 4** — Label: Research partner / Value: Global Research
- **Metric box** (--charcoal bg):
  - Number: 100%
  - Description: Growth in app adoption

---

### Body columns

**Layout:** 3-column grid using separator technique (--lightgrey parent, --white cells)

Column headers: ALL CAPS, 11px, tracked, --midgrey

**Column 1 — The challenge:**
Post-event surveys consistently flagged navigation as a leading source of visitor dissatisfaction. The venue is a 100,000 sqm space across seven halls and three floors, and the signage budget had been reduced — leaving the team looking to a digital solution to fill the gap without increasing overall spend.

**Column 2 — What we did:**
Developed a multi-channel navigation strategy centred on a clearly-positioned "Navigation App" with an interactive floorplan, supported by visible concierge hosts at key locations. Engaged the Global Research team to run structured onsite interviews with visitors — building an evidence base for ongoing investment rather than relying on anecdote.

**Column 3 — The results:**
Twice as many visitors used the navigation app versus the previous year. The onsite research confirmed the continued importance of physical signage, identified specific gaps in the existing approach, and produced a clear multi-year roadmap — including plans for blue-dot indoor positioning in subsequent editions.

---

### Narrative section

Background: --offwhite
Padding: var(--space-2xl) var(--space-lg)

**H3:** The full story

Styling: Archivo Condensed 700, 22px, title case, --charcoal, margin-bottom 16px.

**Body paragraphs** (Archivo 400, 15px, --body, line-height 1.75, max-width 720px, margin-bottom 16px between paragraphs):

Para 1:
Equiphotel Paris is one of Europe's leading hospitality industry trade events, held biennially at Porte de Versailles. With exhibitors and products spread across seven halls over three floors — approximately 100,000 sqm of venue space — navigation is one of the defining factors in whether a visitor has a good experience. For several years running, post-event surveys had flagged it as a top source of dissatisfaction.

Para 2:
The event team faced a specific tension. Physical signage costs had been scrutinised and the signage budget trimmed. At the same time, visitor complaints were persistent. The question on the table was whether a well-designed digital solution could compensate for reduced signage spend without making the experience worse — or whether the evidence would actually argue the other way.

Para 3:
We developed a multi-channel strategy centred on a clearly-branded "Navigation App" featuring an interactive floorplan with search, categories and directions. This was supported by a network of visible concierge hosts positioned at high-traffic points — entrances, hall junctions, and information points — acting as a human fallback for visitors who wouldn't reach for their phone. The app was actively promoted at registration, at entry points, and through QR codes placed around the venue.

Para 4:
The critical decision was to invest in evidence alongside delivery. We engaged the Global Research team to run structured onsite interviews with visitors during the event — not a quick satisfaction survey, but a proper qualitative programme designed to capture how visitors actually navigated the event, where they got stuck, and how they felt about the digital and physical solutions they encountered. The goal was to make the next investment decision on the basis of evidence rather than assumption.

Para 5:
The immediate result was a doubling of navigation app adoption year-on-year. The research output was arguably more valuable in the longer term. It produced a clear, visitor-evidenced view of where the existing approach worked and where it fell short — in particular, reaffirming the continuing importance of physical signage rather than letting digital fully displace it. It also identified specific investments likely to deliver the biggest gains in future editions, including blue-dot indoor positioning to overlay real-time location onto the digital floorplan.

Para 6:
What the team came away with was a multi-year roadmap grounded in visitor evidence — a plan that could be discussed with finance, presented to senior stakeholders, and used to justify continued investment. Navigation shifted from being treated as a recurring cost pressure to being understood as a measurable driver of visitor satisfaction and a legitimate investment priority.

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
| 100% | Growth in app adoption |
| 100,000 sqm | Venue footprint covered |
| Evidence-led | Multi-year roadmap validated |

**Note on the third cell:** "Evidence-led" sits on two lines if necessary — this is fine. It's a descriptive anchor rather than a number, consistent with the "New" cell on the Incosmetics page and the "MRS" cell on the RX page. Archivo Condensed 700 at 32px handles hyphenated compound words comfortably.

---

### Role strip

Background: --white
Padding: 24px 40px
Border-bottom: 0.5px solid --lightgrey

**Content:** [Role label] Product strategy, customer communication strategy, defining the research brief, onboarding the app vendor, and supporting the team through end-to-end delivery.

Role label ("Ade's role:"): 11px, tracked, uppercase, --charcoal, font-weight 700
Rest: 13px, --body

---

### Footer CTA (dark section)

Background: --charcoal

**H2:** Working on something similar?

**Body:** Whether you're scoping a digital wayfinding strategy, reviewing your signage investment, or looking to build an evidence base for future decisions — we'd welcome the conversation.

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
