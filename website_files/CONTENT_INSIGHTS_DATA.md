# CONTENT_INSIGHTS_DATA.md — Using data to improve your event article

Page file: `src/pages/insights/data.astro`
Active nav item: Insights

This page uses the same **article layout** as `/insights/navigation`. Read `CONTENT_INSIGHTS_NAVIGATION.md` first for the layout pattern — this file specifies only the copy and the one structural difference (numbered section callouts with takeaway pullquotes, explained below).

**Source note:** Written for the Allenby Advisory site (UK audience). UK English spelling throughout. Minor source errors corrected, inconsistent capitalisation of "exhibitor" normalised to lowercase, H3-styled summary sentences converted to takeaway callouts.

---

## Updates required to existing pages

### Update `src/pages/insights.astro`

The Articles grid already contains a placeholder link for this article pointing at `/insights/data`. This task makes the route live. Verify the internal link opens in the same tab (no `target="_blank"`). Title, body and publisher on the Insights page card remain unchanged.

---

## New page: `/insights/data`

Astro file-based routing means the URL `/insights/data` requires the file to live at `src/pages/insights/data.astro`.

---

### Breadcrumb

← Insights (href: "/insights")

Same styling as the navigation article.

---

### Article header

Background: --white
Padding: var(--space-2xl) var(--space-lg) var(--space-lg)

**Eyebrow label:** Article

**H1:** Using data to improve your event

**Standfirst (lead paragraph):**
Three ways to turn the data you already have into decisions that move the dials on event revenues — without needing a data science team or a year-long transformation programme.

Same styling as the navigation article standfirst.

**Meta strip** (flex row, gap 24px, padding-top 20px, border-top 0.5px solid --lightgrey, max-width 680px):
- **Publisher item** — Label: Published by / Value: allenby-advisory.com
- **Topic item** — Label: Topic / Value: Data · Measurement · Rebooking

No external publisher link on this article — it was written for the Allenby Advisory site.

---

### Article body

Background: --offwhite
Padding: var(--space-2xl) var(--space-lg)

Single column, max-width 680px. Same typography rules as the navigation article (Archivo 16px, line-height 1.8, --body; H2 Archivo Condensed 700 26px; lists use the 4px accent-dot pattern with 0.5px dividers).

---

### Introduction

**Paragraph 1:**
When I speak to event leaders about data, they often lament that either they don't have enough data to make data-crunching worthwhile, or that they have too much data to know where to start.

**Paragraph 2:**
If you have ever fallen into either category, it probably reflects the common anxiety that we don't have enough time to trawl through the data, or that we don't know where to look first. We doubt that the time spent will be rewarded with tangible outcomes. This article gives some simple tips on what data to collect, and which dials you can move.

---

### H2: Getting started

**Paragraph 1:**
If you have registration data, entry data, session attendance data and post-show survey data, you already have a great start in tracking attendee conversion and satisfaction.

**Paragraph 2:**
Most events also try to capture lead retrieval data and meetings planning data, as well as tracking participant activity on social media. This can help you understand the levels of engagement with exhibitors compared to speakers, and identify influencers in the industry — all of which helps target high-value attendees.

**Paragraph 3:**
Events using visitor-led scanning will also have a large sample of attendee behavioural data from the show floor, based on which attendees have collected information digitally from exhibitors or connected with other participants. This can take the form of visitor badge scanning through the event app, as well as the ability to collect content from exhibitors and sessions by scanning QR codes or using smart badges with sensors. Combined with the data types above, it gives a rich picture of how your event is delivering value.

**Paragraph 4:**
Here are three useful analysis opportunities that large-sample behavioural data from the show floor makes possible.

---

### Numbered section callouts — structural note

The three analysis opportunities below are each structured as a numbered section. Each section uses a distinctive numbered heading pattern (not a standard H2) to make the article's structure scannable.

**Numbered heading layout:** Flex row, align-items baseline, gap 20px, margin-top 56px, margin-bottom 20px.
- **Number:** Archivo Condensed 700, 48px, --lightgrey, line-height 1, letter-spacing 0 — decorative, same pattern as the About page engagement list
- **Heading:** Archivo Condensed 700, 26px, title case, --charcoal, line-height 1.2

Each numbered section ends with a **takeaway callout** (converting the source's H3-styled summary sentences into proper pullquote-style callouts). Layout:
- Margin 24px 0 8px
- Padding 16px 20px
- Background --white
- Border-left 3px solid --accent
- Typography: Archivo 15px, --charcoal, line-height 1.55, font-style normal (not italic — these are takeaways, not quotes)
- Preceded by a small label: "Takeaway" in ALL CAPS, 10px tracked, --midgrey, margin-bottom 8px

---

### Section 01 — What to invest in to attract the right attendees

**Number:** 01
**Heading:** What to invest in to attract the right attendees

**Paragraph 1:**
Your event stands and falls on whether your exhibitors and sponsors get the volume and quality of engagement they need from attendees.

**Paragraph 2:**
But your attendee audience has other goals for the event that contribute to their decision to attend — networking, socialising, hearing from industry peers and experts in talks. These activities may not directly drive engagement with exhibitors, but you need to know whether investing in them attracts the kind of attendees who *do* engage with exhibitors, so you can target the ones who are most valuable as prospects for future events.

**Paragraph 3:**
By combining show-floor behavioural data with session attendance data, you can understand:

**List (accent-dot pattern):**
1. Which attendees visited sessions but did not engage on the show floor.
2. Which attendees visited sessions, then visited exhibitors with related products.
3. Which sessions drew the most attendees who went on to engage well on the show floor.
4. Which sessions were the most popular regardless of attendees' interest categories on the show floor — your hero content.
5. Which exhibitors were the most popular regardless of attendees' declared interest categories — the de facto bellwethers.
6. The impact of putting the most popular speakers at the beginning and end of day slots. Did those attending extend their overall engagement with exhibitors because they arrived earlier and left later?

**Paragraph 4:**
Attendee engagement insights can then help you target your marketing — offering incentives and targeted campaigns to the most valuable attendees, targeting speakers, and offering favourable terms to exhibitors based on their influence on high-value attendees.

**Paragraph 5:**
Remember, though, that just because an attendee didn't visit the show floor this time doesn't mean they won't visit it next time with the right encouragement. After all, session data tells you their topics of interest — so you can create campaigns to target individuals with known interests about exhibitors in that space.

**Takeaway callout:**
Customer satisfaction data can add an extra dimension to behavioural data — you can classify attendees by what they interact with and their average satisfaction. And with accurate behavioural data, you can make surveys shorter and increase the sample size of those completing them.

---

### Section 02 — Increase sales from rebooking

**Number:** 02
**Heading:** Increase sales from rebooking

**Paragraph 1:**
Use data about attendee engagement in real time to inform your sales team — who to help, who to sell to.

**Paragraph 2:**
Anyone managing data and metrics is looking for leading indicators: the metrics that give you insight before the event itself. Registration volume is a leading indicator of attendance.

**Paragraph 3:**
For sales rebooking at the event, you need an indicator that the exhibitor is performing well — so you know whether they are likely to rebook. The key is real-time engagement data from the show floor. By understanding the inbound traffic an exhibitor is getting, and the leads it produces, you can monitor averages and see who is above and below that level. Factoring in stand size helps: create a metric for "average leads per square metre".

**Paragraph 4:**
Having connections data in real time is key. Many modern lead retrieval and content capture systems offload data to the cloud as contacts are captured. More complex visitor-tracking solutions that monitor location via Bluetooth in the attendee's phone may take longer to sync, but should provide near real-time data with a much higher volume of data points — meaning better accuracy at prediction.

**Paragraph 5:**
Another method for improving rebooking is to identify exhibitors who are underperforming and offer support and advice before the end of the event. Live data analysis pushed to salespeople with specific objectives on day two and day three can help triage issues that might otherwise cause dissatisfaction.

**Takeaway callout:**
Active monitoring of exhibitor success, and deployment of sales teams to address low performance during the event, can be the difference in retaining the exhibitor. Identifying high performers with real-time data demonstrates your ability to provide — and prove — value.

---

### Section 03 — Gather industry insights and trends

**Number:** 03
**Heading:** Gather industry insights and trends

**Paragraph 1:**
Understanding what attendees discovered at the event — and which products were more popular than average — can help you spot industry trends.

**Paragraph 2:**
Assess which product categories attendees declared an interest in at registration, then compare this to their show-floor interactions. Consider which categories were most popular relative to their representation on the show floor, and where attendees' actual interest diverged from what they expected to be interested in.

**Paragraph 3:**
This can provide useful insights into what grabbed attendees' attention that they hadn't considered before the event, and into emerging trends for both speaker content and product categories. It can also reveal which products attendees were looking for that perhaps weren't well represented.

**Takeaway callout 1** (this section has two — the source material weighted its takeaways here):
By combining declared interests from registration with visitor and exhibitor connection data, plus session attendance data from the show floor, you can build an accurate picture of which products are over-indexing and under-indexing with attendees.

**Takeaway callout 2:**
The key is category planning. Assigning product categories to exhibitors and sessions, and using the exact same categories for registration interests, allows the datasets to combine into meaningful trend analysis. Without this up-front planning and matching, your investment in implementing and collecting data from different sources may go to waste — especially if attendee interest categories differ from exhibitor product categories.

---

### Pullquote

Sits after Section 03's takeaways, before the conclusion.

**Layout:** Full-width inside the 680px column, margin 48px 0, padding-left 24px, border-left 3px solid --accent.

**Blockquote:** The best approach is to be systematic about the questions you want to answer — then consider what data you have to answer them.

Styling: Archivo 20px, italic, --charcoal, line-height 1.45.

**Cite:** Ade Allenby — Allenby Advisory

Same cite styling as the navigation article.

---

### H2: In summary

**Paragraph 1:**
Show-floor behavioural data can be highly valuable for generating the insights that help you identify sales targets and shape your show to draw the attendees who will engage most with your exhibitors.

**Paragraph 2:**
Visitor-led methods of data capture can provide a much larger sample by putting the ability to connect digitally into the hands of everyone on the show floor — not just exhibitors. Combined with exhibitor lead retrieval, meetings scheduling and digital platform data, it can illustrate customer behaviour at the scale needed for reliable analysis.

**Paragraph 3:**
The best approach is to be systematic: identify the questions you want to answer, consider what data you already have to answer them, and decide what further data-collection activities will give you the larger samples that improve the quality of your results.

---

### Related insights section

Same pattern as the navigation article.

**Section label:** More insights

**H2:** Keep reading

**Card 1:**
- Type: Article
- Title: Event navigation and wayfinding: myth busting
- Body: A challenge to what event teams assume about how visitors navigate — and what the evidence actually says.
- Publisher: Trade Show News Network
- href: /insights/navigation

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

**H2:** Want to talk about your event's data?

**Body:** Whether you're looking to make better use of the data you already collect, design a measurement framework from scratch, or bring in new technology to enrich your understanding of attendees — we'd welcome the conversation.

**Button (light, external):** Book a free 30-minute call → href: `https://calendar.app.google/kscewyXr9JDFXDYK8`, `external={true}`

---

## Animation notes

Apply `class="reveal"` to:
- Each numbered section (reveal as a unit — number, heading, body and callout together)
- The pullquote
- The "In summary" section
- The related insights grid
- The footer CTA

The breadcrumb, article header and opening introduction appear immediately.
