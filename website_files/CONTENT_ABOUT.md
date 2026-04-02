# CONTENT_ABOUT.md — About Page

Page file: `src/pages/about.astro`
Active nav item: About

---

## Hero section

**Layout:** 2-column split — text left, credential card right. Border between columns: 0.5px solid --lightgrey. Right column: --white background.

### Left column

**Eyebrow label:** About Allenby Advisory

**H1:** Why I started Allenby Advisory

**Body paragraphs:**
1. I spent over 10 years working inside the event technology and digital space — with organisers, vendors and delivery teams across the UK and Europe's major trade shows and exhibitions.
2. What I kept seeing was the same pattern: event teams with real ambition for their digital experience, but without the specialist knowledge to navigate the technology landscape confidently.
3. Allenby Advisory exists to give event organising teams access to that expertise precisely when they need it — without the cost and commitment of a full-time hire.

### Right column — credential card

Card: 0.5px border --lightgrey, padding 28px, max-width 320px

**Avatar:**
- Square div (56×56px), bg --charcoal
- Text: "AA" — Julius Sans One, 16px, --white

**Name:** Ade Allenby — Julius Sans One, 17px, --charcoal
(Note: use Julius Sans One here — name is treated as a brand-name-style element)

**Title (ALL CAPS, --midgrey, 11px tracked):** Founder, Allenby Advisory

**Bio items** (list, each: 13px --body, padding 9px 0, border-bottom 0.5px --lightgrey, flex with 4px accent dot):
1. 10+ years in event technology and digital strategy
2. Projects across RX, Imbibe, Equiphotel and others
3. Speaker at EN Marketing Conference 2024
4. Contributor to Event Industry News, Collingwood Group

Animation: credential card slides in from right on page load.

---

## The team section

Background: --white

**Eyebrow label:** The team

**H2:** You're not just getting one consultant

**Body:** Over my years in the industry I've built a close network of specialists who share the same commitment to practical, results-focused work in the events space. I'm the single point of contact — the team assembled around your project reflects exactly what your challenge needs.

**Layout:** 3-column grid, separator technique (--lightgrey parent, --offwhite cells, 0.5px gap)

Each cell: padding 22px, label ALL CAPS 11px tracked --charcoal font-weight 700, description 13px --body.

| Label | Description |
|---|---|
| Digital strategy and product | Roadmapping, feature scoping, platform strategy |
| Marketing and communications | Adoption campaigns, audience engagement, onboarding |
| Tech implementation | Integration, vendor management, delivery oversight |
| Data and insights | Measurement frameworks, performance reporting |
| Onsite operations | Event-day delivery, concierge, logistics |
| Sales and commercial | Exhibitor and sponsor value proposition |

Animation: grid cells stagger in on scroll.

---

## Flexible section

**Layout:** 2-column split — text left, numbered list right. Left: --offwhite bg. Right: --white bg. Border between: 0.5px --lightgrey.

### Left column

**Eyebrow label:** Ways of working

**H2:** Flexible by design

**Body paragraph 1:** We're built to work in the way that suits you — not to fit you into a fixed engagement model.

**Body paragraph 2:** Most engagements start with a free 30-minute conversation. No pitch, no pressure — just an honest discussion about your challenge.

**Button (primary):** Book a free call → href: "/#contact"

### Right column — numbered engagement list

List items (each: flex row, number left + content right, padding 18px 0, border-bottom 0.5px --lightgrey):

**Number style:** Archivo Condensed 700, 24px, --lightgrey (decorative, not --midgrey)

**Item 1:**
- Number: 01
- Label (ALL CAPS, 11px, tracked, --charcoal, font-weight 700): Strategic advisory
- Description: A few hours a month. Independent perspective, on demand. No retainer, no commitment.

**Item 2:**
- Number: 02
- Label: Project delivery
- Description: Scoped to your timeline and budget. Full accountability from brief to results.

**Item 3:**
- Number: 03
- Label: Embedded support
- Description: Regular involvement through your event cycle — part of the team without the overhead.

---

## Footer CTA (dark section)

**H2:** Start with a conversation

**Body:** The free 30-minute consultation is focused entirely on your challenge — honest, no-obligation, and genuinely useful.

**Button (light):** Book a free consultation → href: "/#contact"

**Email line:** Or email directly: ade@allenby-advisory.com (11px, tracked, uppercase, color #666; email link color #6b9fc5)
