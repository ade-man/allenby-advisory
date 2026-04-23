# CONTENT_HOME.md — Homepage

Page file: `src/pages/index.astro`

---

## Navigation (shared — from Nav.astro)

Links: Services | Client successes | About | Insights
CTA button: "Book a consultation" → href: "#contact" (update to Calendly URL when available)
Active page: Home (no nav item needed — logo is home link)

---

## Hero section

**Eyebrow label:** Event technology and digital

**H1:**
Event technology decisions are [accent]expensive to get wrong.[/accent]

Note: wrap "expensive to get wrong." in `<span style="color: var(--accent)">` — this is the only coloured word in the heading.

**Body:**
Allenby Advisory helps event leaders choose, implement and get results from the right technology — without the learning curve, the wasted budget, or the failed launches.

**CTA — primary button:** Book a free 30-minute consultation → href: "#contact"
**CTA — ghost button:** See our work → href: "/client-successes"

Animation: H1 slides up on page load. Body and CTAs fade in with 0.15s and 0.3s delays respectively.

---

## Section: Who this is for

**Section label:** Who this is for

**H2:** You know what you need. You need someone who's done it before.

**Audience box** (white card, accent left-border):
- Para 1: You're an Event Director, Marketing Manager or Digital Leader responsible for the technology that makes your event work — for attendees, exhibitors and sponsors.
- Para 2: Maybe you're replacing a platform. Maybe you're launching new digital capabilities. Maybe you've invested in tech that isn't delivering results.
- Para 3 (italic, --charcoal): "This is exactly the kind of challenge Allenby Advisory was built for."

Animation: audience box reveals on scroll.

---

## Section: What we do

**Section label:** What we do

**Layout:** 3-column grid using ServiceTile component. Grid uses separator technique (0.5px gaps, --lightgrey parent background).

### Tile 1
- Number: 01
- Category: Advisory
- Title: Technology sourcing and selection
- Body: Seen too many demos? We cut through the noise. Drawing on 10+ years of hands-on experience, we identify the right tools for your event and help you avoid costly mistakes.
- Link text: Learn more → href: "/services#advisory"

### Tile 2
- Number: 02
- Category: Delivery
- Title: Project delivery and implementation
- Body: From scoping to go-live. We manage the vendor relationship, oversee integration, and make sure your team is equipped to get the most from new platforms.
- Link text: Learn more → href: "/services#delivery"

### Tile 3
- Number: 03
- Category: Engagement
- Title: Audience engagement and adoption
- Body: Technology is only valuable if people use it. We build the communication and onboarding strategies that drive adoption and measurable outcomes.
- Link text: Learn more → href: "/services#engagement"

Animation: tiles stagger in on scroll (0s, 0.1s, 0.2s delays).

---

## Section: Network strip (dark)

**Background:** --charcoal (dark section pattern)

**Section label:** Why Allenby Advisory

**H2:** One point of contact. A whole team behind it.

**Body:** When you work with Allenby Advisory, you're not just engaging one consultant. Ade Allenby brings 10 years of specialist experience — and a close network of specialists assembled around your specific project.

**Skill pills** (flex row, wrapping):
- Digital strategy
- Tech implementation
- Event marketing
- Data and insights
- Onsite operations
- Vendor management

Animation: H2 fades in, skill pills stagger in on scroll.

---

## Section: Recent work

**Section label:** Recent work

**H2:** Problems solved. Results measured.

**Layout:** 2-column grid using CaseCard component.

### Card 1
- Result badge: 100% growth in app adoption
- Title: Equiphotel Paris — Visitor navigation strategy
- Event tag: 6 halls · 3 floors · Paris
- Body: Persistent negative visitor feedback on navigation was turned into a measurable multi-year improvement programme — validated with onsite research.
- Link: Read the full story → href: "/client-successes#equiphotel"

### Card 2
- Result badge: Serious meetings. Party atmosphere. Both delivered.
- Title: Imbibe Live London — 1-2-1 Meetings Programme
- Event tag: On-trade drinks show · London
- Body: A show known for its convivial atmosphere ran structured, productive business meetings — with the tools in place to prove they happened.
- Link: Read the full story → href: "/client-successes#imbibe"

Animation: cards reveal on scroll.

---

## Section: What clients say

**Section label:** What clients say

**Layout:** 2-column grid using Testimonial component.

### Testimonial 1
- Quote: Ade's deep and practical knowledge of event tech means he has an instinct for the right solutions. First and foremost, he's motivated by helping organiser and user teams get optimum value from a project.
- Name: Mark Maydon
- Role: Director, Crowd Connected

### Testimonial 2
- Quote: Grip was the ideal solution for our young, mobile audience. We needed something that would work easily through their phones — and Ade made sure it did.
- Name: Sonja Van Praag
- Role: Publishing & Events Director, Imbibe

Animation: testimonials reveal on scroll.

---

## Section: Insights

**Section label:** Insights

**H2:** Practical thinking from the field.

**Layout:** 3-column grid using InsightItem component. Grid uses separator technique.

### Insight 1
- Type: Article
- Title: Developing a 1-2-1 meetings strategy: key insights for success
- Body: The factors that actually determine whether a meetings programme delivers value.
- href: https://collingwood.group/resources/developing-a-1-2-1-meetings-strategy-key-insights-for-success/

### Insight 2
- Type: Podcast
- Title: Scaling with event tech — Event Industry News
- Body: How technology can help events scale — what works, what doesn't.
- href: https://www.eventindustrynews.com/podcasts/scaling-with-event-tech

### Insight 3
- Type: Article
- Title: Event navigation and wayfinding: myth busting
- Body: What the evidence says about how visitors actually navigate large events.
- href: /insights#navigation

**See all link:** See all insights → href: "/insights" (11px, tracked, uppercase, --accent)

---

## Footer CTA section (dark)

**id:** contact
**Background:** --charcoal

**H2:** Not sure whether you need help right now?

**Body:** Tell us about your current challenge or opportunity. Our free 30-minute consultation is no-obligation and focused entirely on your event.

**Button (light variant):** Book your free consultation → href: (Calendly URL — leave as "#" for now)

**Email line:** Or email Ade directly: ade@allenby-advisory.com (11px, tracked, uppercase, color #666; email link color #6b9fc5)

---

## Footer (shared — from Footer.astro)

Left: "Allenby Advisory" — Julius Sans One, 13px
Right: "Event technology and digital · © 2025" — 11px, tracked, uppercase, --midgrey
