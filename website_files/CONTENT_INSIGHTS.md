# CONTENT_INSIGHTS.md — Insights Page

Page file: `src/pages/insights.astro`
Active nav item: Insights

---

## Page header

**Eyebrow label:** Ideas and thinking

**H1:** Insights

**Body:** Practical thinking on event technology, digital strategy and audience engagement — drawn from projects, research and conversations across the industry.

---

## Featured article section

Background: --white
Layout: 2-column — article info left, pullquote right

### Left column

**Label (ALL CAPS, --midgrey):** Featured

**Tag (ALL CAPS badge, 0.5px border --lightgrey):** Article

**Publisher (ALL CAPS, --midgrey, 11px tracked):** Collingwood Group

**H2:** Developing a 1-2-1 meetings strategy: key insights for success

**Body:** The factors that actually determine whether a meetings programme delivers value — from matchmaking logic to onsite facilitation. A practical guide for event teams thinking seriously about how to structure their programme.

**Read link (ALL CAPS, --accent):** Read the article → href: https://collingwood.group/resources/developing-a-1-2-1-meetings-strategy-key-insights-for-success/

### Right column — pullquote

Styling: border-left 3px solid --accent, padding-left 20px

**Blockquote (Archivo 18px, italic, --charcoal):**
"The difference between a meetings programme that works and one that doesn't is almost never the technology."

**Cite (11px, tracked, uppercase, --midgrey):** Ade Allenby — Allenby Advisory

---

## Articles section

**H2:** Articles

Layout: 3-column grid using separator technique (--lightgrey parent, --white cells)

Each cell uses InsightItem component.

### Article 1

**id:** navigation
- Type tag: Article
- Title: Event navigation and wayfinding: myth busting
- Body: A challenge to what event teams assume about how visitors navigate — and what the evidence actually says.
- Publisher (ALL CAPS, --midgrey): allenby-advisory.com
- href: /insights/navigation (placeholder — article page to be added later)

### Article 2

- Type tag: Article
- Title: Using data to improve your event
- Body: Where to start if you want to move from gut feel to data-informed decisions. Practical, not theoretical.
- Publisher: allenby-advisory.com
- href: /insights/data (placeholder)

### Article 3

- Type tag: Article
- Title: Astrology, my mother-in-law and the future of events
- Body: How COVID permanently shifted attendee expectations for face-to-face events.
- Publisher: LinkedIn
- href: https://www.linkedin.com/pulse/astrology-my-mother-in-law-future-events-ade-allenby/

---

## Speaking, podcasts and panels section

**H2:** Speaking, podcasts and panels

Layout: List. Each item: 3-column grid row (type badge 80px | content 1fr | link auto), padding 16px 0, border-bottom 0.5px --lightgrey.

Type badge: bg --charcoal, color --white, 10px tracked uppercase, padding 4px 8px, no border-radius.
Title: 13px, --charcoal, font-weight 700.
Description: 13px, --body.
Link: 11px, tracked, uppercase, --accent.

### Item 1
- Type: Podcast
- Title: Scaling with event tech — Event Industry News
- Description: How technology can help events scale. What works, what doesn't, and where organisers typically go wrong.
- Link text: Listen →
- href: https://www.eventindustrynews.com/podcasts/scaling-with-event-tech

### Item 2
- Type: Panel
- Title: Community marketing panel — Exhibition News
- Description: Hosting a panel at EN Marketing Conference 2024 on social selling and community building.
- Link text: Read →
- href: https://www.linkedin.com/pulse/panel-discussion-social-selling-future-innovations-ogxye/

### Item 3
- Type: Webinar
- Title: Small details matter — Ctrl + Alt + Event
- Description: Fine-tuning your events: tech integration and behavioural insights for event success.
- Link text: Watch →
- href: https://www.linkedin.com/events/smalldetailsmatter-fine-tuningy7168621170567692289/comments/

---

## Footer CTA (dark section)

**H2:** Want to talk through something you've read?

**Body:** Most good conversations start with a question. If something here has sparked a thought about your own event, we'd be happy to explore it together.

**Button (light):** Book a free 30-minute call → href: "/#contact"
