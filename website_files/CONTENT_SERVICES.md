# CONTENT_SERVICES.md — Services Page

Page file: `src/pages/services.astro`
Active nav item: Services

---

## Page header

**Eyebrow label:** What we do

**H1:** Services

**Body:** Allenby Advisory works with event organising teams in three ways. Choose the level of support that fits where you are right now.

---

## Service blocks

Layout: each service is a 2-column row — narrow left label column (200px fixed), wide right content column.
- Left column: --offwhite background, right border 0.5px --lightgrey
- Right column: --white background
- Each block: border-bottom 0.5px --lightgrey

### Service 1

**id:** advisory

Left column:
- Number label: 01
- Service type (Archivo Condensed 700, title case, 20px): Advisory
- Badge (ALL CAPS tag, bg --charcoal, white text): On demand

Right column:
- **H3:** Strategic input, when you need it
- **Body:** You have internal resource but need specialist knowledge to make the right decisions. We provide senior expertise on demand — reviewing your technology landscape, interrogating supplier proposals, and pressure-testing your digital roadmap.
- **Fit label (ALL CAPS, --midgrey):** This is right for you if:
- **Fit list items:**
  1. You're evaluating new technology and want an independent view
  2. You need a sounding board for a digital strategy decision
  3. You want someone who's been in the room with these vendors before
- **How it works strip** (--offwhite bg, 0.5px border): **How it works:** Flexible engagement from a few hours a month. No long-term commitment required.
- **Button (primary):** Let's talk → href: "/#contact"

---

### Service 2

**id:** delivery

Left column:
- Number label: 02
- Service type: Project delivery
- Badge: End to end

Right column:
- **H3:** From brief to results
- **Body:** You have a clear outcome to achieve — a new platform to implement, a feature to build, a programme to launch — but not the specialist capacity to deliver it well. We scope the project, manage the vendor relationship, and see it through to a successful outcome at your event.
- **Fit label:** This is right for you if:
- **Fit list items:**
  1. You're replacing an existing technology platform
  2. You're launching a new audience-facing feature — meetings, navigation, awards, sessions
  3. You need a project lead with deep event tech experience to drive delivery
- **How it works strip:** **How it works:** Project-based engagement scoped to your timeline and budget.
- **Button (primary):** Tell us about your project → href: "/#contact"

---

### Service 3

**id:** engagement

Left column:
- Number label: 03
- Service type: Capability building
- Badge: 4–12 weeks

Right column:
- **H3:** Getting more from what you already have
- **Body:** Sometimes the platform isn't the problem — the problem is adoption, engagement and results. We work with your team to build the strategy and onboarding journey that turns existing tech investment into real outcomes for your audience.
- **Fit label:** This is right for you if:
- **Fit list items:**
  1. You've invested in a platform that isn't delivering expected engagement
  2. Your team needs to build confidence around a tool
  3. You want to move from "we have the tech" to "our audience uses the tech"
- **How it works strip:** **How it works:** Structured programme, typically 4–12 weeks around your event cycle.
- **Button (primary):** Let's explore this → href: "/#contact"

---

## Capabilities section

**H2:** Areas we work across

**Layout:** 4-column grid using separator technique (--lightgrey parent, 0.5px gap). Each cell: --white bg, padding 20px.

Cell labels are ALL CAPS 11px tracked. Descriptions are body text 13px.

| Label | Description |
|---|---|
| Event app strategy | Sourcing, scoping and implementation |
| Meetings programmes | 1-2-1 matchmaking and scheduling |
| Navigation and wayfinding | Digital and physical onsite experience |
| Speaker and content tech | Programme platform selection |
| Data and audience insight | Measurement frameworks and reporting |
| Adoption campaigns | Communication and onboarding strategy |
| Digital roadmapping | Customer journey to tech requirements |
| Vendor management | Sourcing, evaluation and contracting |

Animation: grid items reveal on scroll (staggered).

---

## Footer CTA (dark section)

**H2:** Not sure which applies to you?

**Body:** Most conversations start with a problem, not a service category. Book a free 30-minute call and we'll work it out together.

**Button (light):** Book a free consultation → href: "/#contact"
