# CONTENT_CLIENT_SUCCESSES_CLARION_AI.md — Clarion AI Assistant Case Study

Page file: `src/pages/client-successes/clarion-ai-assistant.astro`
Active nav item: Client successes

This page follows the same extended structure as the Incosmetics Global and RX Global Research case studies (breadcrumb → header → top section → 3-column body → narrative → quote → outcomes → role strip → footer CTA). Read `CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md` and `CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md` first to understand the layout patterns.

---

## Voice — third person

This case study is written in the third person, referring to the principal as "Ade Allenby", "Ade", or "he". It does **not** use "we", "us" or "our". This is a deliberate departure from the current voice of the rest of the site (which uses "we") and may be extended to other pages later — see `TASKS_ADDENDUM_VOICE_AUDIT.md` for the full audit of first-person-plural usage across the site.

Where the source copy is signed off by the client, the signed wording is preserved verbatim. Framing and outcomes copy around the signed block is written in third person.

---

## Partner model — how Visual Hive is credited

Visual Hive were engaged directly by Clarion as the delivery partner. They were selected on Ade's guidance and reported into him through the programme — but the contractual relationship ran between Clarion and Visual Hive. This is an important distinction from the RX Global / Sound HQ setup (where The Sound HQ were recruited and managed as part of Ade's engagement) and should be reflected in the language used. Specifically:

- Ade selected and recommended Visual Hive as the delivery partner
- Clarion contracted Visual Hive directly
- Visual Hive reported into Ade for programme delivery
- The programme was led by Ade in partnership with Bogdan Maran's team at Visual Hive

Avoid wording that implies Allenby Advisory subcontracted or managed Visual Hive commercially.

---

## Updates required to existing pages

### 1. Add card to `src/pages/client-successes.astro` project index

Add a CaseCard for the Clarion AI Assistant project to the project index grid. This card becomes the sixth card in the index — the grid is already set to 3-column (updated when the Connect case study was added), so no grid change is required.

**Card:**
- Result badge: TSNN Best Innovation (B2C) 2025
- Title: Clarion Events — AI Assistant product development
- Event tag: 7 iterations · Europe and US · B2B and B2C
- Body: An AI matchmaking and concierge assistant was developed across seven iterations — deployed at live events in Europe and the US, and recognised with a leading industry innovation award.
- Link: Read the full story → href: "/client-successes/clarion-ai-assistant"

---

## New page: `/client-successes/clarion-ai-assistant`

---

### Breadcrumb

← Client successes (href: "/client-successes")

Styling: font-size 11px, tracked, uppercase, --midgrey. Link: --accent, no underline.
Add margin-bottom 18px above eyebrow.

---

### Page header

**Eyebrow label:** Case study — product development

**H1:** Clarion Events: AI Assistant product development

**Body:** How a small-scale matchmaking experiment became a multi-event, multi-channel AI product — developed across seven iterations, deployed at live events in Europe and the US, and recognised by Trade Show News Network as the Best Innovation on a B2C show in 2025.

---

### Top section

**Layout:** 2-column — text left (1fr), meta card right (240px fixed)
Background: --white

Left column:
- **Label (ALL CAPS, --midgrey, 11px tracked):** The project in brief
- **H2:** From proof of concept to award-winning product
- **Body:** Clarion Events had an early-stage matchmaking prototype and needed to turn it into a fully-fledged product. Ade brought in a product development approach — scoping use cases, mapping the target customer journey, and running a structured programme of iterations. On Ade's guidance, Clarion engaged Visual Hive as the delivery partner, with Bogdan Maran's team reporting into Ade across seven live-event iterations.
- **Button (primary):** Get in touch about a similar project → href: "/#contact"

Right column (meta card — --offwhite bg, 0.5px border):
- **Meta item 1** — Label: Client / Value: Clarion Events
- **Meta item 2** — Label: Scope / Value: 7 iterations · Europe and US
- **Meta item 3** — Label: Service type / Value: Product development
- **Meta item 4** — Label: Delivery partner / Value: Visual Hive
- **Metric box** (--charcoal bg):
  - Number: 2025
  - Description: TSNN Best Innovation on a B2C show

Note on meta item 4 label: the word "Partner" has been changed to "Delivery partner" to accurately reflect the commercial relationship (Clarion contracted Visual Hive directly; Visual Hive reported into Ade on delivery).

---

### Body columns

**Layout:** 3-column grid using separator technique (--lightgrey parent, --white cells)

Column headers: ALL CAPS, 11px, tracked, --midgrey

**Column 1 — The challenge:**
Clarion had proved in a mid-2024 test that event content and exhibitor data could power AI matchmaking recommendations for visitors. The challenge was turning that proof of concept into a product: identifying the use cases that would deliver real value, designing a customer journey around them, and validating performance at scale across commercially live events.

**Column 2 — What Ade did:**
Brought in a product development approach — defining use cases, mapping the target customer journey, and identifying Visual Hive as the right delivery partner. Clarion engaged Visual Hive directly on Ade's recommendation, with Bogdan Maran's team reporting into Ade through the programme. Each of seven successive iterations was deployed at a live event, each with a specific test objective — from internal evaluation, through controlled customer testing, to full production deployment at scale.

Note on column header: the header for Column 2 is "What Ade did" rather than "What we did" — a third-person variant to be carried through consistently on this page.

**Column 3 — The results:**
The AI Assistant now operates across seven access channels — including website, native app, WhatsApp, SMS and email — with proven scale at up to ten calls per minute and over 9,000 interactions at a single event. Personalised recommendation emails hit a 57%+ open rate with 11%+ click-through. TSNN recognised the Rose City Comic Con deployment with the 2025 Best Innovation on a B2C show award.

---

### Narrative section

Background: --offwhite
Padding: var(--space-2xl) var(--space-lg)

**H3:** The full story

Styling: Archivo Condensed 700, 22px, title case, --charcoal, margin-bottom 16px.

**Important:** the paragraphs below are the Clarion-signed copy reproduced verbatim. The source material — the table of iterations, the factual claims, and the quoted TSNN award citation — are reproduced without edit. Do not rewrite or abbreviate this section without going back to Clarion.

**Body paragraphs** (Archivo 400, 15px, --body, line-height 1.75, max-width 720px, margin-bottom 16px between paragraphs):

Para 1 (signed copy — verbatim):
In mid 2024, Clarion Events had undertaken a small scale test with a development agency to demonstrate the ability to use event content and data from exhibitor and session listings to provide matchmaking recommendations to visitors.

Para 2 (signed copy — verbatim):
Ade Allenby was brought in to apply a product development approach to taking this forward into a fully-fledged product. Initially reviewing use cases and mapping a target customer journey, under Ade's guidance, Clarion partnered with Bogdan Maran and his team at Visual Hive to support the scoping and delivery of a programme to test and validate the product. Visual Hive were working on AI agent technology and had extensive domain knowledge of the events industry.

Para 3 (signed copy — verbatim):
Using the latest in AI development tools to allow for rapid prototyping and allow for customisation across Clarion tech stack and individual events (Langflow, DataStax, N8N) and leveraging the latest LLMs (Open AI Azure, Anthropic, Grok) they supported Clarion in evolving the capabilities of an AI Assistant built to Clarion's specifications.

---

#### Iterations table

Sits between Para 3 and Para 4 of the signed narrative. This is the table of seven iterations from the Clarion source copy, reproduced verbatim.

**Layout:** full-width inside the 720px reading column. HTML `<table>` with:
- Header row: --offwhite bg, padding 10px 14px, ALL CAPS 10px tracked --midgrey, font-weight 700, text-align left, border-bottom 0.5px solid --lightgrey
- Body rows: --white bg, padding 14px, border-bottom 0.5px solid --lightgrey, font-size 13px, line-height 1.55, --body, vertical-align top
- Column 1 (Iteration): 56px fixed, Archivo Condensed 700, 16px, --charcoal, text-align center
- Column 2 (Event): ~220px, 13px, --charcoal, font-weight 700
- Column 3 (Test outcomes): 1fr, 13px, --body

Test outcomes column uses short line breaks — each outcome on its own line, separated by a 4px vertical gap. Keep visually compact.

Table margin: 24px 0 32px.

**Table content (verbatim from signed copy):**

| Iteration | Event | Test outcomes |
|---|---|---|
| 1 | DTX/UCX 2023 (historical data) | Internal evaluation. Session recommendation comparisons. |
| 2 | Enlit Europe 2024 (historical data) | Customer interviews on product value and user interface. Successful addition of speaker data. |
| 3 | ICE Gaming 2025 (live data) | Matchmaking and event help capability. Controlled customer testing. Proven live usage. |
| 4 | MAU Las Vegas 2025 (live data) | Available to all attendees (live production systems). Simple app integration. Login and user profile functionality. |
| 5 | Coffee Fest LA 2025 (live data) | Multi-channel: WhatsApp, SMS, email + website/web app. Assistant outbound matchmaking campaign (52.7% open rate). Scaled to 5,000 recommendations. |
| 6 | Rose City Comiccon (live data) | Proven at scale with up to 10 calls per minute and 9,000 interactions. Application to B2C format including paid tickets and multi-track content. AI augmented vendor profiles. |
| 7 | ICE/iGB Live 2026 (live data) | Co-located events, dual answer capability based on badge. "Anonymous" and logged-in version to improve adoption. Built-in floorplan and directory. |

Mobile: table may scroll horizontally inside its container (`overflow-x: auto`) rather than restructure — preserving the three-column reading is more important than fitting the full width on a small screen.

---

Para 4 (signed copy — verbatim):
Through a rigorous approach to understanding customer value and how to drive engagement at key touchpoints of the customer journey, Clarion's partnership with Allenby Advisory and Visual Hive was able to deliver successive leaps in functionality and quality of customer experience. A low-touch content ingestion and testing process was developed to ensure limited impact on event team resources.

Para 5 (signed copy — verbatim):
Clarion now stands out amongst its peers in its preparedness to deploy AI agents across its business across different touchpoint in the customer journey.

Para 6 (signed copy — verbatim):
Validation of the product strategy and implementation came from Trade Show News Network in the US who honoured the Rose City Comiccon team with Best Innovation on a B2C show 2025.

---

### Quote section

Background: --offwhite

The quote sits immediately after Para 6 of the narrative and is the published TSNN award citation, reproduced verbatim from the signed copy.

**Quote:** "Rose City Comic Con reimagined fan engagement through 'Rosy,' an AI-powered virtual assistant that served as a 24/7 concierge for attendees. Integrated into the event website and optimized for mobile, Rosy handled thousands of inquiries — from celebrity schedules to badge pickup — while personalizing responses and offering empathetic communication. Beyond improving the attendee experience, Rosy provided actionable insights for organizers, revealing trends and opportunities for future engagement. This innovative approach reduced customer service volume, enhanced operational efficiency, and positioned Rose City Comic Con as a leader in leveraging AI to create smarter, more connected fan experiences."

**Cite:** Trade Show News Network — Best Innovation on a B2C show, 2025

Styling: blockquote — Archivo 16px, italic, --charcoal, border-left 3px solid --accent, padding-left 20px, max-width 620px. Cite — 11px, tracked, uppercase, --midgrey, padding-left 23px, margin-top 12px, font-style normal.

Note on US spelling: the quote is a US publication citation and retains US English ("optimized", "personalizing", "organizers") — do not anglicise. This matches the site convention established on the navigation article.

Note on length: this quote is longer than the ~40-word quotes elsewhere on the site. It is reproduced in full because it is the signed, award-citing source for the project's primary external validation. The blockquote's max-width widens slightly from 600px to 620px to accommodate without looking cramped.

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
| 7 | Access channels — web, app, SMS, WhatsApp, email and more |
| 57%+ | Open rate on personalised recommendation emails |
| 77% | Customer feedback rating on answer quality |

These proof points are drawn from the signed copy ("7 Access channels", "57%+ open rate 11%+ clickthrough rate of personalised recommendation emails", "77% Feedback rating on answer quality").

---

### Role strip

Background: --white
Padding: 24px 40px
Border-bottom: 0.5px solid --lightgrey

**Content:** [Role label] Product strategy, use case definition, customer journey mapping, selection and recommendation of Visual Hive as delivery partner, iteration planning across seven live events, and programme leadership with Bogdan Maran's team at Visual Hive reporting into Ade on delivery.

Role label ("Ade's role:"): 11px, tracked, uppercase, --charcoal, font-weight 700
Rest: 13px, --body

Note on framing: the wording "selection and recommendation of Visual Hive as delivery partner" and "reporting into Ade on delivery" is deliberate — it avoids implying Allenby Advisory subcontracted Visual Hive commercially, while accurately reflecting Ade's role in partner selection and programme leadership.

---

### Footer CTA (dark section)

Background: --charcoal

**H2:** Working on something similar?

**Body:** Whether you're scoping an AI product from scratch, looking to turn a prototype into a live deployment, or thinking through how AI agents might fit your customer journey — Ade would welcome the conversation.

Note on copy: the existing footer CTA pattern across the site uses "we'd welcome the conversation". This page replaces that with "Ade would welcome the conversation" to maintain third-person voice within the case study. If the broader voice audit (see `TASKS_ADDENDUM_VOICE_AUDIT.md`) results in site-wide conversion to third person, align this phrasing with the rest of the site at that point.

**Button (light, external):** Book a free 30-minute call → href: `https://calendar.app.google/kscewyXr9JDFXDYK8`, `external={true}`

---

## Animation notes

Apply `class="reveal"` to:
- The top section (case-top)
- Each body column
- The narrative section (including the iterations table)
- The quote section
- The outcomes metrics row
- The role strip

The breadcrumb and page header should appear immediately (no reveal delay) as they are above the fold.

---

## Items to confirm before implementation

- **Iterations table layout on mobile.** Spec allows horizontal scroll; if Cline / review prefers a stacked card layout on small screens, that is an acceptable alternative — agree the pattern before implementation.
- **Visual Hive link.** If Visual Hive's website URL is to be linked from the meta card value, confirm the target URL. Current spec does not link the partner name.
- **Third-person voice precedent.** This is the first page on the site using third-person voice consistently. If the broader audit leads to rewriting existing pages, this case study's framing copy (intro body, body-column headers, footer CTA) should be reviewed for consistency with the new site-wide voice.
