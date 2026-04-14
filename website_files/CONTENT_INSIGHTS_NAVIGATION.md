# CONTENT_INSIGHTS_NAVIGATION.md — Event navigation and wayfinding article

Page file: `src/pages/insights/navigation.astro`
Active nav item: Insights

This page is an **article layout** — distinct from the case study layout. Articles are long-form reading: single-column prose, one pullquote, no metric cards, no 3-column project grids. Read this file alongside `CONTENT_INSIGHTS_DATA.md` (same template, different copy) and the existing `insights.astro` to understand where it fits.

**Source note:** This article was originally published in Trade Show News Network (TSNN), a US publication. US English spelling is preserved throughout. Minor source errors corrected.

---

## Updates required to existing pages

### Update `src/pages/insights.astro`

The current Articles section has two placeholder links pointing at `/insights/navigation` and `/insights/data`. Both placeholders become live pages with this task and the data article task. The href values on those cards already match the new routes, so no href changes are needed — but verify both links open in the same tab (internal links, no `target="_blank"`).

Also update Article 1 (the navigation myth-busting article) on the Insights page so its **publisher** reads `Trade Show News Network` rather than `allenby-advisory.com`, reflecting the original publication. Leave the title and body unchanged.

---

## New page: `/insights/navigation`

Astro file-based routing means the URL `/insights/navigation` requires the file to live at `src/pages/insights/navigation.astro`. The `insights/` subdirectory under `pages/` will need to be created.

---

### Breadcrumb

← Insights (href: "/insights")

Styling: font-size 11px, tracked, uppercase, --midgrey. Link: --accent, no underline.
Margin-bottom 18px above eyebrow.

---

### Article header

Background: --white
Padding: var(--space-2xl) var(--space-lg) var(--space-lg)

**Eyebrow label:** Article

**H1:** Event navigation and wayfinding: myth busting our way to success

Styling: Archivo Condensed 700, 44px, title case, --charcoal, line-height 1.08, max-width 780px, margin-bottom 20px.

**Standfirst (lead paragraph):**
Navigating a trade show can be a daunting experience for visitors. The repetitive grid layout, the lack of reference points and the sheer size of events can make it hard to find your way — especially when there are multiple halls.

Styling: Archivo 400, 19px, --charcoal, line-height 1.55, max-width 680px, margin-bottom 28px.

**Meta strip** (flex row, gap 24px, padding-top 20px, border-top 0.5px solid --lightgrey, max-width 680px):
- **Publisher item** — Label (9px tracked uppercase --midgrey): Originally published / Value (11px tracked uppercase --charcoal, font-weight 700): Trade Show News Network — linked to `https://www.tsnn.com/blog/event-navigation-and-wayfinding-myth-busting-our-way-success` with `target="_blank" rel="noopener noreferrer"`. Link color --accent, no underline.
- **Date item** — Label: Published / Value: 17 May 2023
- **Topic item** — Label: Topic / Value: Navigation · Wayfinding

Meta item layout: stacked (label on top, value below). Gap between stack: 4px.

---

### Article body

Background: --offwhite
Padding: var(--space-2xl) var(--space-lg)

Body content is centered, single column, max-width 680px. All prose uses Archivo 400, 16px, line-height 1.8, --body.

H2s: Archivo Condensed 700, 26px, title case, --charcoal, margin-top 48px, margin-bottom 16px.
Paragraphs: margin-bottom 18px.
Lists: no default bullets. Each `<li>` uses the 4px accent dot pattern (`::before` pseudo-element, 4px × 4px square, bg --accent, margin-right 12px, vertical-align middle). List items: padding 8px 0, border-bottom 0.5px solid --lightgrey. Last item: no border.

**Paragraph 1:**
Post-event surveys often capture verbatim feedback from visitors that cite navigation as a leading source of dissatisfaction from the event experience.

**Paragraph 2:**
A key obstacle for event organizers in solving this problem is that we are prone to thinking about the visitor journey in the way we want it to happen, and overlook the idiosyncrasies of what attending an event can actually be like.

---

#### Contrast panels section

This is the one visual flourish of the page. Two side-by-side panels showing the gap between organizer expectations and visitor reality.

**Layout:** 2-column grid, gap 0.5px, parent bg --lightgrey (separator technique). Each panel: --white bg, padding 28px. On mobile (max-width 768px): stack to single column.

Panel headers: ALL CAPS, 11px, tracked, --midgrey, margin-bottom 16px, padding-bottom 12px, border-bottom 0.5px solid --lightgrey.
Inside each panel, the intro line is in Archivo Condensed 700, 17px, --charcoal, title case, margin-bottom 14px.
Lists inside panels: same accent-dot pattern as body lists, but font-size 14px.

**Left panel:**

- **Header (ALL CAPS):** The expectation
- **Intro:** What we want visitors to do
- **List items:**
  1. Meticulously plan a route around the event, ensuring they visit everything they are interested in.
  2. Work out how long it is going to take them to get from meeting to meeting based on distance between exhibitors.
  3. Remember when content sessions are being held and at what time when they are out browsing the show floor.
  4. Familiarize themselves with the floor-plan on a "you are here" board to find a specific exhibitor, then remember it for their next meeting.
  5. Study the layout of the hall and stand numbering system to find their way.

**Right panel:**

- **Header (ALL CAPS):** The reality
- **Intro:** What visitors actually do (we've all been there)
- **List items:**
  1. Think about where their first meeting is located only the moment they get issued with their badge.
  2. Miss meetings and content sessions they wanted to attend because they got distracted on the show floor and had no idea how long it was going to take to find the exhibitor, theatre or networking lounge.
  3. Forget to pick up a show guide — or worse, get to the entrance to find they have all gone.
  4. Consult the "you are here" board in a cursory fashion to find a certain exhibitor, then quickly forget the route as soon as they are on the show floor.
  5. Get confused when stands aren't numbered sequentially — and when many stands don't display stand numbers at all.

Padding around this section inside the 680px column: margin 32px 0.

---

**Paragraph after panels:**
These difficulties are compounded by the fact that most of us have largely outsourced navigation in our everyday lives to our smartphones and the artificial intelligence that helps us pick the best route to the best-rated restaurant, avoiding the worst of the traffic. Orienting ourselves in an unfamiliar environment using a paper-based map is, to many, a lost art.

**Paragraph:**
It seems obvious, then, that providing an experience that mimics what the smartphone delivers — specifically for inside a trade-show venue — would be the optimal solution. The challenge is that GPS doesn't work inside an event hall, and the temporary nature of exhibitor stands means they aren't shown on Google or Apple maps anyway. You need a solution that compensates for this: in essence, an interactive floorplan with indoor positioning, such as the combined solution from ExpoFP and Crowd Connected, among others.

---

### H2: What your visitors actually need

**List (accent-dot pattern):**
1. A floor-plan that can easily be accessed on a smartphone and has been specifically designed for visitor wayfinding — not an exhibitor space-allocation plan created by operations for contractors to build the show.
2. Easy ways to find this digital floor-plan — for example, QR codes placed around the show and a bold button link on your homepage on the days of the show.
3. Search and routing that enables any show component and venue facility to be found.
4. The familiar blue dot overlaid on the digital floor-plan showing current location, telling you precisely where you are the moment you realize you need to be somewhere else.
5. Real-time location updated as you move about, so you can quickly see that you have made a wrong turn — or decide to take a stop along the route.
6. Reminders about meetings and speaker sessions saved to your calendar that alert you in time to get there (and suggest the best route).

---

### Pullquote

Sits after the list above, before the analogue signage section.

**Layout:** Full-width inside the 680px column, margin 40px 0, padding-left 24px, border-left 3px solid --accent.

**Blockquote:** Orienting ourselves in an unfamiliar environment using a paper-based map is, to many, a lost art.

Styling: Archivo 20px, italic, --charcoal, line-height 1.45.

**Cite (below quote):** Ade Allenby — Allenby Advisory

Cite styling: 11px, tracked, uppercase, --midgrey, margin-top 12px, font-style normal.

---

### H2: Don't abandon the analogue

**Paragraph:**
It's always helpful to have highly visible analogue directional signage, however good your digital wayfinding solution is. That might include overhead aisle numbering, consistent booth-number display, sequential and logical booth numbering (far from the case at too many shows) and high-level signage for theatres, meeting spaces, washrooms and food outlets.

**Paragraph:**
Budget for this is often trimmed — but be aware of the cost of lost and confused visitors reflected in visitor and exhibitor NPS and retention rates.

---

### H2: Navigation is an investment, not an overhead

**Paragraph:**
Navigation at your event should be considered as much an investment as marketing the event itself. It is fundamental to ensuring positive outcomes for visitors and exhibitors — and the economic return is that your marketing budget will go further next year as retention rates increase.

---

### Related insights section

Background: --white
Padding: var(--space-2xl) var(--space-lg)
Border-top: 0.5px solid --lightgrey

**Section label (ALL CAPS, --midgrey):** More insights

**H2:** Keep reading

Styling: Archivo Condensed 700, 28px, title case, --charcoal, margin-bottom 32px.

**Layout:** 2-column grid using separator technique (--lightgrey parent, --white cells, 0.5px gap). Use InsightItem component.

**Card 1:**
- Type: Article
- Title: Using data to improve your event
- Body: Where to start if you want to move from gut feel to data-informed decisions. Practical, not theoretical.
- Publisher: allenby-advisory.com
- href: /insights/data

**Card 2:**
- Type: Article
- Title: Developing a 1-2-1 meetings strategy: key insights for success
- Body: The factors that actually determine whether a meetings programme delivers value.
- Publisher: Collingwood Group
- href: https://collingwood.group/resources/developing-a-1-2-1-meetings-strategy-key-insights-for-success/
- External link: true (open in new tab)

---

### Footer CTA (dark section)

Background: --charcoal

**H2:** Thinking about navigation at your event?

**Body:** Whether you're scoping a digital wayfinding platform, reviewing your physical signage strategy, or trying to build the evidence base for investment — we'd welcome the conversation.

**Button (light, external):** Book a free 30-minute call → href: `https://calendar.app.google/kscewyXr9JDFXDYK8`, `external={true}`

---

## Animation notes

Apply `class="reveal"` to:
- The contrast panels section (reveal as a pair)
- The pullquote
- Each H2 section after the first
- The related insights grid
- The footer CTA

The breadcrumb, article header and opening paragraphs appear immediately (above the fold, no reveal delay).
