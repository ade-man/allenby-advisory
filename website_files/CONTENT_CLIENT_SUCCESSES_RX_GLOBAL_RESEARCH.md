# CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md — RX Global Customer Research Case Study

Page file: `src/pages/client-successes/rx-global-research.astro`
Active nav item: Client successes

This page follows the same structure as the Incosmetics Global case study in `CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md`. Read that file and `CONTENT_CLIENT_SUCCESSES.md` first to understand the layout patterns.

---

## Updates required to existing pages

### 1. Add card to `src/pages/client-successes.astro` project index

Add a CaseCard for RX Global Customer Research to the project index grid. Update the grid to accommodate the additional card.

**Card:**
- Result badge: 88% awareness amongst senior event managers
- Title: RX Global — Attendee behavioural archetypes
- Event tag: Global · 68 events · 10 countries
- Body: We led a global research programme that produced an award-winning framework for understanding attendee needs — adopted across every business unit worldwide.
- Link: Read the full story → href: "/client-successes/rx-global-research"

---

## New page: `/client-successes/rx-global-research`

---

### Breadcrumb

← Client successes (href: "/client-successes")

Styling: font-size 11px, tracked, uppercase, --midgrey. Link: --accent, no underline.
Add margin-bottom 18px above eyebrow.

---

### Page header

**Eyebrow label:** Case study — research and strategy

**H1:** RX Global: attendee behavioural archetypes

**Body:** How a global qualitative and quantitative research programme produced an award-winning framework for understanding attendee needs — and changed how one of the world's largest event organisations thinks about its customers.

---

### Top section

**Layout:** 2-column — text left (1fr), meta card right (240px fixed)
Background: --white

Left column:
- **Label (ALL CAPS, --midgrey, 11px tracked):** The project in brief
- **H2:** From fragmented insight to a common global language
- **Body:** RX needed a shared framework for understanding B2B event attendees across its global portfolio. We led a multi-country research programme — qualitative interviews followed by a global quantitative survey — that produced a set of behavioural archetypes now used in every business unit worldwide.
- **Button (primary):** Get in touch about a similar project → href: "/#contact"

Right column (meta card — --offwhite bg, 0.5px border):
- **Meta item 1** — Label: Client / Value: RX (Reed Exhibitions)
- **Meta item 2** — Label: Scope / Value: 10 countries · 68 events
- **Meta item 3** — Label: Service type / Value: Research and strategy
- **Meta item 4** — Label: Agency / Value: The Sound HQ
- **Metric box** (--charcoal bg):
  - Number: 88%
  - Description: Awareness amongst senior event managers

---

### Body columns

**Layout:** 3-column grid using separator technique (--lightgrey parent, --white cells)

Column headers: ALL CAPS, 11px, tracked, --midgrey

**Column 1 — The challenge:**
RX was rebuilding its core event platform and needed to establish what B2B event attendees had in common globally — across markets as different as the US, UK, France, UAE and China. Without a shared understanding of attendee needs, the digital toolset risked being built around assumptions rather than evidence.

**Column 2 — What we did:**
Recruited and managed the research agency, coordinated ten country business units, developed the methodology with RX insight teams, and oversaw qualitative interviews filmed across multiple markets. The findings were validated with a quantitative survey across 68 events globally.

**Column 3 — The results:**
The research produced a set of behavioural archetypes that won the 2017 Market Research Society Award for Best B2B Paper. A programme of 19 global workshops embedded the framework across the organisation, achieving 88% awareness amongst senior event managers within a year.

---

### Narrative section

Background: --offwhite
Padding: var(--space-2xl) var(--space-lg)

**H3:** The full story

Styling: Archivo Condensed 700, 22px, title case, --charcoal, margin-bottom 16px.

**Body paragraphs** (Archivo 400, 15px, --body, line-height 1.75, max-width 720px, margin-bottom 16px between paragraphs):

Para 1:
As part of a global initiative to rebuild the core event platform, the brief was to find out what B2B event attendees had in common — regardless of geography, sector or event format. The goal was a framework that could underpin a standardised yet modular digital toolset, applicable across the entire RX portfolio.

Para 2:
The first task was to recruit the right research partner. We selected The Sound HQ and worked closely with them and RX insight teams to develop a methodology that would work across culturally diverse markets. Ten country business units took part — including the US, UK, France, UAE and China — each requiring coordination, briefing and local adaptation.

Para 3:
The qualitative phase involved filmed interviews with attendees across multiple markets — designed not just to capture data, but to produce compelling material that could communicate the findings internally. Interview briefs were developed collaboratively and reviewed at each stage to ensure consistency and depth.

Para 4:
The qualitative findings were then validated through a global quantitative survey polling 68 events. The Sound HQ brought tools and techniques that resulted in a set of findings recognised by the Market Research Society — winning the 2017 Award for Best B2B Paper.

Para 5:
A key output recognised by the judges was a set of behavioural archetypes. These went beyond digital tool preferences to describe the different ways attendees get value from a live event — from structured meeting-seekers to serendipitous explorers. The archetypes provided a language that event teams could use to think about their audience in a more nuanced, evidence-based way.

Para 6:
To embed the framework across the organisation, we delivered a programme of 19 workshops around the world. These weren't passive presentations — they were working sessions designed to help event teams apply the archetypes to their own events, audiences and commercial models. When senior event managers were surveyed the following year, 88% were aware of the framework and its applications.

Para 7:
The archetypes were subsequently integrated into RX's registration and post-event survey processes, allowing event teams to assess which attendee goals mattered most at each show — and to match those goals against the tools and experiences on offer. This became a key driver in improving Net Promoter Scores across the portfolio.

---

### Quote section

Background: --offwhite

**Quote:** "This work not only gives us a common global language around customer behaviours, but the insights are helping drive ambitious transformation into a data and digital driven business by providing clear evidence of common needs."

**Cite:** Chet Burchett — CEO, RX

Styling: blockquote — Archivo 16px, italic, --charcoal, border-left 3px solid --accent, padding-left 20px, max-width 600px. Cite — 11px, tracked, uppercase, --midgrey, padding-left 23px.

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
| 88% | Awareness amongst senior managers |
| MRS | Best B2B Paper 2017 |
| 19 | Global workshops delivered |

---

### Role strip

Background: --white
Padding: 24px 40px
Border-bottom: 0.5px solid --lightgrey

**Content:** [Role label] Research programme leadership, agency recruitment and management, methodology development, coordination of 10 country business units, global workshop delivery, and integration into registration and survey processes.

Role label ("Ade's role:"): 11px, tracked, uppercase, --charcoal, font-weight 700
Rest: 13px, --body

---

### Footer CTA (dark section)

Background: --charcoal

**H2:** Working on something similar?

**Body:** Whether you're looking to understand your audience better, build an evidence base for digital investment, or align a global team around a shared framework — we'd welcome the conversation.

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
