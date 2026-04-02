# CONTENT_CLIENT_SUCCESSES.md — Client Successes Page

Page file: `src/pages/client-successes.astro`
Active nav item: Client successes

---

## Page header

**Eyebrow label:** Our work

**H1:** Client successes

**Body:** Every project starts with a problem. Here's how we've helped event teams solve theirs.

---

## Project index (card grid)

**Index label (ALL CAPS, --midgrey):** All projects

**Layout:** 2-column card grid using CaseCard component.

### Card 1
- Result badge: 100% growth in app adoption
- Title: Equiphotel Paris — Visitor navigation
- Event tag: Paris · Trade show · 6 halls
- Body: Turned persistent negative visitor feedback on navigation into a validated, multi-year improvement programme.
- Link: Read the full story → href: "#equiphotel"

### Card 2
- Result badge: Serious meetings. Party atmosphere.
- Title: Imbibe Live London — 1-2-1 meetings
- Event tag: London · On-trade drinks show · B2B
- Body: Delivered structured, measurable business meetings inside a show known for its vibrant, sociable atmosphere.
- Link: Read the full story → href: "#imbibe"

---

## Case study 1 — Equiphotel Paris

**id:** equiphotel

### Top section

**Layout:** 2-column — text left (1fr), meta card right (240px fixed)
Background: --white

Left column:
- **Label (ALL CAPS, --midgrey):** Case study — project delivery
- **H2:** Equiphotel Paris: visitor navigation strategy
- **Body:** We turned one of the event's most persistent pain points — visitor navigation across a 6-hall, 3-floor venue — into a measurable, multi-year improvement programme.
- **Button (primary):** Get in touch about a similar project → href: "/#contact"

Right column (meta card — --offwhite bg, 0.5px border):
- **Meta item 1** — Label: Event / Value: Equiphotel Paris
- **Meta item 2** — Label: Venue / Value: Porte de Versailles
- **Meta item 3** — Label: Service type / Value: Project delivery
- **Metric box** (--charcoal bg):
  - Number: 100%
  - Description: Growth in app adoption

Meta labels: 10px, tracked, uppercase, --midgrey
Meta values: 13px, --charcoal, font-weight 700

---

### Body columns

**Layout:** 3-column grid using separator technique (--lightgrey parent, --white cells)

Column headers: ALL CAPS, 11px, tracked, --midgrey

**Column 1 — The challenge:**
Post-event surveys consistently flagged navigation as a source of visitor dissatisfaction. The signage budget had been reduced — the team hoped a digital solution could fill the gap for less cost.

**Column 2 — What we did:**
Developed a multi-channel strategy centred on a clearly-positioned "Navigation App" with an interactive floorplan, supported by visible concierge hosts at key locations. Engaged the Global Research team to conduct onsite visitor interviews — building an evidence base for ongoing investment.

**Column 3 — The results:**
Twice as many visitors used the navigation app versus the previous year. Onsite research validated the importance of physical signage and produced a clear multi-year roadmap including blue-dot indoor positioning.

---

### Quote section

Background: --offwhite

**Quote:** "Grip was the ideal solution to introduce both an app and a matchmaking solution to the young and mobile Imbibe Live audience. We needed a solution which would work easily through their phones."

**Cite:** Sonja Van Praag — Publishing & Events Director, Imbibe

Styling: blockquote — Archivo 16px, italic, --charcoal, border-left 3px solid --accent, padding-left 20px, max-width 600px. Cite — 11px, tracked, uppercase, --midgrey, padding-left 23px.

---

### Role strip

Background: --white

**Content:** **Ade's role:** Product strategy, customer communication strategy, defining the research brief, onboarding the app vendor, and supporting the team through end-to-end delivery.

"Ade's role:" label: 11px, tracked, uppercase, --charcoal, font-weight 700
Rest: 13px, --body

---

## Case study 2 — Imbibe Live

**id:** imbibe

### Top section

Left column:
- **Label:** Case study — project delivery
- **H2:** Imbibe Live London: 1-2-1 meetings programme
- **Body:** We helped a show known for its convivial atmosphere deliver a high-functioning meetings programme for its most commercially important attendees.
- **Button (primary):** Get in touch about a similar project → href: "/#contact"

Right column (meta card):
- **Meta item 1** — Label: Event / Value: Imbibe Live London
- **Meta item 2** — Label: Venue / Value: Olympia London
- **Meta item 3** — Label: Service type / Value: Project delivery
- **Metric box:**
  - Number: B2B
  - Description: Meetings programme delivered

---

### Body columns

**Column 1 — The challenge:**
Imbibe Live is the on-trade drinks show — brands and suppliers meet the owners, managers and staff of restaurants, bars and pubs. The event has a reputation for being convivial and fun. The challenge: how do you run credible, productive business meetings in an atmosphere increasingly dominated by tastings and socialising?

**Column 2 — What we did:**
Working with the Imbibe event team and the RXUK Digital team, we scoped and implemented the Grip matchmaking app, supported by the creation of a dedicated networking lounge. The app allowed attendees to get personalised suggestions of who to meet, pre-schedule meetings, or arrange them spontaneously on the day.

**Column 3 — The results:**
The programme successfully enabled the event's target VIP buyer audience to have structured, productive meetings in an environment designed for the purpose. The concierge function added genuine value — intervening when meetings were at risk and capturing real-time feedback from users.

---

### Quote section

Background: --offwhite

**Quote:** "Grip was the ideal solution to introduce both an app and a matchmaking solution to the young and mobile Imbibe Live audience. We needed a solution which would work easily through their phones, especially as due to the nature of their jobs they are not at their desks very often."

**Cite:** Sonja Van Praag — Publishing & Events Director, Imbibe

---

### Role strip

Background: --white

**Content:** **Ade's role:** Product strategy, customer communication strategy, onboarding the app vendor, and supporting the team through end-to-end delivery.

---

## Footer CTA (dark section)

**H2:** Working on something similar?

**Body:** Whether you're launching a meetings programme, tackling navigation, or thinking through your next digital initiative — we'd welcome the conversation.

**Button (light):** Book a free 30-minute call → href: "/#contact"
