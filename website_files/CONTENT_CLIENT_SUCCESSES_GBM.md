# CONTENT_CLIENT_SUCCESSES_GBM.md — Global Banking Markets Case Study

Page file: `src/pages/client-successes/global-banking-markets.astro`
Active nav item: Client successes

This page follows the same extended structure as the Incosmetics Global and RX Global Research case studies (breadcrumb → header → top section → 3-column body → narrative → outcomes → role strip → footer CTA). Read `CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md` and `CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md` first to understand the layout patterns.

This project was delivered in partnership with Adam Price (The Growth Architect), who led the HubSpot implementation. Ade's role was engagement lead and client relationship — see the role strip for details. This mirrors the way The Sound HQ is credited on the RX Global Research page.

---

## Updates required to existing pages

### 1. Add card to `src/pages/client-successes.astro` project index

Add a CaseCard for Global Banking Markets to the project index grid. The grid should already be set to a 2×2 layout from Task 6c — this fifth card means the grid either becomes 3+2 (2×2 plus a centred card) or switches to `repeat(3, 1fr)` as a 3+2 layout. **Recommended:** switch to `grid-template-columns: repeat(3, 1fr)` and accept a 3-over-2 layout, with the fifth card sitting on its own on the second row, left-aligned. A future sixth case study will complete the grid.

**Card:**
- Result badge: Single source of truth across every global event
- Title: Global Banking Markets — HubSpot as the central data platform
- Event tag: Global · Financial conferences and festivals · Multi-country
- Body: We rebuilt the technology stack around HubSpot — replacing a fragmented set of spreadsheets, legacy CRM and disconnected tools with a unified, automated data platform.
- Link: Read the full story → href: "/client-successes/global-banking-markets"

---

## New page: `/client-successes/global-banking-markets`

---

### Breadcrumb

← Client successes (href: "/client-successes")

Styling: font-size 11px, tracked, uppercase, --midgrey. Link: --accent, no underline.
Add margin-bottom 18px above eyebrow.

---

### Page header

**Eyebrow label:** Case study — systems and data

**H1:** Global Banking Markets: HubSpot as the central source of truth

**Body:** How a fragmented, spreadsheet-driven event operation was rebuilt around HubSpot — turning sponsor management, attendee data, website content and revenue reporting into a single, automated system supporting events across multiple countries.

---

### Top section

**Layout:** 2-column — text left (1fr), meta card right (240px fixed)
Background: --white

Left column:
- **Label (ALL CAPS, --midgrey, 11px tracked):** The project in brief
- **H2:** From fragmented spreadsheets to a single connected platform
- **Body:** Global Banking Markets runs large-scale financial industry conferences and festivals across multiple countries, bringing together senior executives, sponsors and industry innovators. Before the project, each part of the business — sponsors, attendees, website, finance — operated in isolation. We rebuilt the stack around HubSpot as the central source of truth, with custom objects, a client portal, API integrations and automated website content driven directly from CRM data.
- **Button (primary):** Get in touch about a similar project → href: "/#contact"

Right column (meta card — --offwhite bg, 0.5px border):
- **Meta item 1** — Label: Client / Value: Global Banking Markets
- **Meta item 2** — Label: Scope / Value: Multi-country conferences and festivals
- **Meta item 3** — Label: Service type / Value: Systems and data
- **Meta item 4** — Label: Delivery partner / Value: The Growth Architect
- **Metric box** (--charcoal bg):
  - Number: 500+
  - Description: Automated workflows in production

---

### Body columns

**Layout:** 3-column grid using separator technique (--lightgrey parent, --white cells)

Column headers: ALL CAPS, 11px, tracked, --midgrey

**Column 1 — The challenge:**
The existing stack couldn't keep up with the scale or complexity of a global event portfolio. The legacy CRM couldn't handle the data model. Sponsor, attendee and session information lived across spreadsheets, shared drives and disconnected third-party tools. Every sponsor listing, attendee update or session change required manual intervention — and marketing and sales teams had no reliable view of revenue or event performance.

**Column 2 — What we did:**
Replaced the legacy CRM with HubSpot and designed a relational data model using custom objects for Attendees, Sponsors, Festivals and Events. Built a secure client portal for sponsors and speakers to self-serve registrations, uploads and VIP invites. Integrated HubSpot bidirectionally with registration and event management systems, and rebuilt the website so its content is driven live from CRM records.

**Column 3 — The results:**
HubSpot became the single source of truth for every sponsor, speaker, attendee and event. Manual spreadsheet updates and site edits were eliminated. Finance and leadership gained real-time visibility into revenue and sponsorship performance. The platform scales across the entire global portfolio — with more than 500 automated workflows and thousands of daily API calls running the operation quietly in the background.

---

### Narrative section

Background: --offwhite
Padding: var(--space-2xl) var(--space-lg)

**H3:** The full story

Styling: Archivo Condensed 700, 22px, title case, --charcoal, margin-bottom 16px.

**Body paragraphs** (Archivo 400, 15px, --body, line-height 1.75, max-width 720px, margin-bottom 16px between paragraphs):

Para 1:
Global Banking Markets organises senior-level financial industry conferences and festivals across multiple countries. The audiences are senior executives, sponsors and industry innovators — commercially valuable, time-poor and used to being treated well. The operational reality behind the scenes was a long way from the polish of the events themselves.

Para 2:
Before the project, the technology stack had grown organically over years. A legacy CRM sat at the centre but couldn't represent the actual shape of the business. Sponsor contracts lived in one system, attendee data in another, session and speaker information in spreadsheets, and website content in a CMS disconnected from all of it. Every change — a new sponsor, an updated session, a VIP invite — required someone to update several places by hand.

Para 3:
The brief was not just to replace the CRM. It was to rebuild the operational backbone of the business around a single source of truth, so that every team — sales, marketing, operations, finance — was working from the same underlying data.

Para 4:
We chose HubSpot as the platform and designed a relational data model using custom objects for Attendees, Sponsors, Festivals and Events. This was the critical decision: rather than forcing event data into a standard contacts-and-companies shape, the model mirrors how the business actually thinks — events belong to festivals, sessions belong to events, speakers are associated with sessions, sponsors are tied to specific activations. Everything links back cleanly.

Para 5:
On top of this foundation, we built a secure client portal for sponsors and speakers. They can register themselves, upload their own details, manage sponsorship information and handle staff and VIP invites — all writing directly back into HubSpot. The manual back-and-forth of email chains and spreadsheet chasing simply stopped.

Para 6:
The website was rebuilt to pull its content directly from HubSpot. When a new sponsor is confirmed, a session is updated, or a speaker is added, the change appears on the public site automatically — no manual CMS edits, no version drift. The website became a live view of CRM data rather than a separate asset that needed to be kept in sync.

Para 7:
Behind the scenes, more than 500 automated workflows and thousands of daily API calls keep the operation running. Registration systems and event management tools integrate bidirectionally, so data flows in both directions without human intervention. Session management, speaker associations, sponsor deliverables and revenue tracking all happen inside one connected system.

Para 8:
The transformation is as much organisational as technical. With HubSpot as the source of truth, finance and leadership gained real-time visibility into revenue and sponsorship performance. The operations team stopped spending time on manual admin and started spending it on the things that actually grow the business — relationship building, sponsor experience and delivering the events themselves.

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
| 1 | Single source of truth across the business |
| 500+ | Automated workflows in production |
| Live | Website driven directly from CRM data |

---

### Role strip

Background: --white
Padding: 24px 40px
Border-bottom: 0.5px solid --lightgrey

**Content:** [Role label] Engagement lead and client relationship, scoping the operating model and data requirements, and working alongside delivery partner Adam Price (The Growth Architect), who led the HubSpot implementation, custom object design, API integrations and automation build.

Role label ("Ade's role:"): 11px, tracked, uppercase, --charcoal, font-weight 700
Rest: 13px, --body

---

### Footer CTA (dark section)

Background: --charcoal

**H2:** Working on something similar?

**Body:** Whether you're replacing a legacy CRM, unifying fragmented event data, or trying to move from manual admin to an automated operating model — we'd welcome the conversation.

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
