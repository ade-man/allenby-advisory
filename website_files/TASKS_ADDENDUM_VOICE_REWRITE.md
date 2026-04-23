# TASKS_ADDENDUM_VOICE_REWRITE.md — Apply voice rewrite to existing pages

This task implements the voice rules agreed in `TASKS_ADDENDUM_VOICE_AUDIT.md`. It can be completed at any point — it is a pure content change with no structural, layout, or styling implications.

---

## Task 14 — Apply voice rewrite to existing content

**Goal:** Update copy on five existing pages to follow the agreed voice rules. The changes are content-only — no components, no styles, no layout, no routes are affected. No build errors are expected.

**Read first:** `TASKS_ADDENDUM_VOICE_AUDIT.md` for the rules. The five replacement content files supplied with this task (see "Replacement files" below) already reflect all required changes; Cline works from those, not from the old source.

---

### Voice rules (summary)

1. **Default site voice is "we"** — stays on Homepage, Services, About, Insights index, Insights article pages, and Client successes index page header (noting the index eyebrow and intro are the exception — see Rule 3).
2. **Case study pages use third person** ("Ade", "Ade Allenby", "he") — applies to Equiphotel, Imbibe, Incosmetics, RX Global, and Clarion AI.
3. **Card summaries and the client successes index frame are voice-neutral** — passive voice or client-subject phrasing, no "we" and no "Ade".
4. **Body column 2 header** on third-person case study pages reads "What Ade did:" not "What we did:".
5. **Footer CTAs** on third-person case study pages close with "Ade would welcome the conversation" instead of "we'd welcome the conversation".
6. **Verbatim signed copy and client testimonials are preserved** — the Sonja Van Praag, Mark Maydon, Chet Burchett, and TSNN quotes stay exactly as-is.

---

### Pages affected

| Page file | Rendered URL | What changes |
|---|---|---|
| `src/pages/index.astro` | `/` | Two case card body texts (homepage "Recent work" section) |
| `src/pages/client-successes.astro` | `/client-successes` | Eyebrow label, page intro body, Equiphotel top/column-2/column-2-body, Imbibe top/column-2/column-2-body, footer CTA body |
| `src/pages/client-successes/incosmetics-global.astro` | `/client-successes/incosmetics-global` | Project index card body, top section body, column 2 header, narrative Para 3, footer CTA body |
| `src/pages/client-successes/rx-global-research.astro` | `/client-successes/rx-global-research` | Project index card body, top section body, column 2 header, narrative Para 2, narrative Para 6, footer CTA body |
| `src/pages/client-successes/clarion-ai-assistant.astro` | `/client-successes/clarion-ai-assistant` | Project index card body only (if the page hasn't been built yet, build from the updated content file; if it has been built using the earlier version, swap just the card body on `client-successes.astro` and leave the case study page intact — it was already correctly voiced) |

Pages **not affected** (for the avoidance of doubt): `services.astro`, `about.astro`, `insights.astro`, `insights/navigation.astro`, `insights/data.astro`.

---

### Replacement content files

This task comes with five updated content spec files as drop-in replacements for the originals in the project folder. Apply the updated versions to Cline's workspace, then implement the corresponding page-level changes listed below.

1. `CONTENT_HOME.md` (was: lines 114, 121)
2. `CONTENT_CLIENT_SUCCESSES.md` (was: lines 10, 14, 52, 77, 117, 135, 136, 165)
3. `CONTENT_CLIENT_SUCCESSES_INCOSMETICS.md` (was: lines 20, 56, 79, 105, 160)
4. `CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md` (was: lines 20, 56, 79, 102, 114, 175)
5. `CONTENT_CLIENT_SUCCESSES_CLARION_AI.md` (was: card body only)

If Cline prefers an in-place edit pattern over replacement, the explicit change list below is equivalent and can be applied directly to the `.astro` pages without consulting the content files at all.

---

### Explicit change list — apply these edits to the .astro files

#### `src/pages/index.astro`

**Homepage "Recent work" section — Card 1 body (Equiphotel card):**

Find:
```
We turned negative visitor feedback on navigation into a measurable multi-year improvement programme — validated with onsite research.
```
Replace with:
```
Persistent negative visitor feedback on navigation was turned into a measurable multi-year improvement programme — validated with onsite research.
```

**Homepage "Recent work" section — Card 2 body (Imbibe card):**

Find:
```
We helped a show known for its convivial atmosphere run structured, productive business meetings — and built the tools to prove they happened.
```
Replace with:
```
A show known for its convivial atmosphere ran structured, productive business meetings — with the tools in place to prove they happened.
```

---

#### `src/pages/client-successes.astro`

**Page header eyebrow label:**

Find:
```
Our work
```
Replace with:
```
Recent work
```

**Page header body:**

Find:
```
Every project starts with a problem. Here's how we've helped event teams solve theirs.
```
Replace with:
```
Every project starts with a problem. Here's how event teams solved theirs.
```

**Equiphotel case study — top section body:**

Find:
```
We turned one of the event's most persistent pain points — visitor navigation across a 6-hall, 3-floor venue — into a measurable, multi-year improvement programme.
```
Replace with:
```
Ade turned one of the event's most persistent pain points — visitor navigation across a 6-hall, 3-floor venue — into a measurable, multi-year improvement programme.
```

**Equiphotel case study — Column 2 header:**

Find:
```
What we did:
```
Replace with:
```
What Ade did:
```

*(This text appears twice in this file — once for Equiphotel, once for Imbibe. Both instances receive the same change. Cline should locate both and replace each.)*

**Imbibe case study — top section body:**

Find:
```
We helped a show known for its convivial atmosphere deliver a high-functioning meetings programme for its most commercially important attendees.
```
Replace with:
```
Ade helped a show known for its convivial atmosphere deliver a high-functioning meetings programme for its most commercially important attendees.
```

**Imbibe case study — Column 2 body:**

Find:
```
Working with the Imbibe event team and the RXUK Digital team, we scoped and implemented the Grip matchmaking app, supported by the creation of a dedicated networking lounge.
```
Replace with:
```
Working with the Imbibe event team and the RXUK Digital team, Ade scoped and implemented the Grip matchmaking app, supported by the creation of a dedicated networking lounge.
```

**Footer CTA body:**

Find:
```
Whether you're launching a meetings programme, tackling navigation, or thinking through your next digital initiative — we'd welcome the conversation.
```
Replace with:
```
Whether you're launching a meetings programme, tackling navigation, or thinking through your next digital initiative — Ade would welcome the conversation.
```

**Do not change:** the Sonja Van Praag quotes on lines 89 and 147 (testimonials, preserved verbatim).

---

#### `src/pages/client-successes/incosmetics-global.astro`

**Project index card body** (this card lives on `client-successes.astro`, not on the Incosmetics page itself — but the card copy is specified in the Incosmetics content file):

Find:
```
We scaled a niche feature-zone product into a show-wide NFC lead capture system — and turned it into a new exhibitor revenue stream.
```
Replace with:
```
A niche feature-zone product was scaled show-wide into an NFC lead capture system — and turned into a new exhibitor revenue stream.
```

This change is applied to the Incosmetics `CaseCard` on `client-successes.astro`.

**Top section body:**

Find:
```
The event had an existing self-scan product limited to feature zones. We identified an opportunity to scale it show-wide using NFC badging technology — turning a niche feature into a commercially significant, opt-out exhibitor product.
```
Replace with:
```
The event had an existing self-scan product limited to feature zones. Ade identified an opportunity to scale it show-wide using NFC badging technology — turning a niche feature into a commercially significant, opt-out exhibitor product.
```

**Column 2 header:**

Find:
```
What we did:
```
Replace with:
```
What Ade did:
```

**Narrative Para 3:**

Find:
```
Working with the Global Innovation Team and the UK Digital Team, we trialled NFC-enabled devices that allow visitors to tap their badge at any exhibitor stand.
```
Replace with:
```
Working with the Global Innovation Team and the UK Digital Team, Ade trialled NFC-enabled devices that allow visitors to tap their badge at any exhibitor stand.
```

**Footer CTA body:**

Find:
```
Whether you're looking to improve exhibitor lead capture, launch a digital content strategy, or scale an existing product — we'd welcome the conversation.
```
Replace with:
```
Whether you're looking to improve exhibitor lead capture, launch a digital content strategy, or scale an existing product — Ade would welcome the conversation.
```

---

#### `src/pages/client-successes/rx-global-research.astro`

**Project index card body** (change applied to the RX Global `CaseCard` on `client-successes.astro`):

Find:
```
We led a global research programme that produced an award-winning framework for understanding attendee needs — adopted across every business unit worldwide.
```
Replace with:
```
A global research programme produced an award-winning framework for understanding attendee needs — adopted across every business unit worldwide.
```

**Top section body:**

Find:
```
RX needed a shared framework for understanding B2B event attendees across its global portfolio. We led a multi-country research programme — qualitative interviews followed by a global quantitative survey — that produced a set of behavioural archetypes now used in every business unit worldwide.
```
Replace with:
```
RX needed a shared framework for understanding B2B event attendees across its global portfolio. Ade led a multi-country research programme — qualitative interviews followed by a global quantitative survey — that produced a set of behavioural archetypes now used in every business unit worldwide.
```

**Column 2 header:**

Find:
```
What we did:
```
Replace with:
```
What Ade did:
```

**Narrative Para 2:**

Find:
```
The first task was to recruit the right research partner. We selected The Sound HQ and worked closely with them and RX insight teams to develop a methodology that would work across culturally diverse markets.
```
Replace with:
```
The first task was to recruit the right research partner. Ade selected The Sound HQ and worked closely with them and RX insight teams to develop a methodology that would work across culturally diverse markets.
```

**Narrative Para 6:**

Find:
```
To embed the framework across the organisation, we delivered a programme of 19 workshops around the world.
```
Replace with:
```
To embed the framework across the organisation, Ade delivered a programme of 19 workshops around the world.
```

**Footer CTA body:**

Find:
```
Whether you're looking to understand your audience better, build an evidence base for digital investment, or align a global team around a shared framework — we'd welcome the conversation.
```
Replace with:
```
Whether you're looking to understand your audience better, build an evidence base for digital investment, or align a global team around a shared framework — Ade would welcome the conversation.
```

**Do not change:** the Chet Burchett quote on line 125 (testimonial, preserved verbatim).

---

#### `src/pages/client-successes.astro` — Clarion AI card body only

The Clarion AI case study page itself (`src/pages/client-successes/clarion-ai-assistant.astro`) is already correctly voiced under Rules 2, 4 and 5 — do not touch it.

The only change is the Clarion card body on the `client-successes.astro` project index:

Find:
```
Ade led the product development of an AI matchmaking and concierge assistant across seven iterations — deployed at live events in Europe and the US, and recognised with a leading industry innovation award.
```
Replace with:
```
An AI matchmaking and concierge assistant was developed across seven iterations — deployed at live events in Europe and the US, and recognised with a leading industry innovation award.
```

If the Clarion case study page has not yet been built at the time of this task, use the updated `CONTENT_CLIENT_SUCCESSES_CLARION_AI.md` supplied with this task when building it — the card body is already corrected in that updated file.

---

### Pages and content deliberately unchanged

For clarity, these items have been reviewed and are intentionally staying as-is:

- `CONTENT_HOME.md` lines 28, 49, 51, 59, 66, 73, 185 (hero ghost button, "What we do" section heading and eyebrow, service tile bodies, footer CTA body) — Rule 1
- Homepage line 140 — Mark Maydon testimonial quote — client voice
- `CONTENT_SERVICES.md` — entire file — Rule 1
- `CONTENT_ABOUT.md` — entire file — Rule 1 plus preserved first-person-singular hero content
- `CONTENT_INSIGHTS.md` line 121 — footer CTA — Rule 1 (this is the insights index, not a case study)
- `CONTENT_CLIENT_SUCCESSES.md` lines 89, 147 — Sonja Van Praag testimonials — client voice
- `CONTENT_CLIENT_SUCCESSES_RX_GLOBAL_RESEARCH.md` line 125 — Chet Burchett testimonial — client voice
- `CONTENT_INSIGHTS_NAVIGATION.md` — rhetorical "we" in article body is industry voice; footer CTA stays Rule 1
- `CONTENT_INSIGHTS_DATA.md` — rhetorical "we" in article body is reader voice; footer CTA stays Rule 1
- All body column 1 headers ("The challenge:") and column 3 headers ("The results:") — unchanged by this rewrite
- All metric boxes, outcomes sections, role strips, meta cards — unchanged
- The Clarion AI case study page itself — already correctly voiced

---

### Verification

1. `/` — Homepage "Recent work" section shows two cards with the new voice-neutral copy (no "we helped" / "we turned")
2. `/client-successes` — page eyebrow reads "Recent work"; page intro reads "Every project starts with a problem. Here's how event teams solved theirs."; all four card summaries (Equiphotel, Imbibe, Incosmetics, RX Global) are voice-neutral; five cards present in total (or six if Clarion is already included)
3. `/client-successes` — Equiphotel top section reads "Ade turned…"; Column 2 header reads "What Ade did:" (both Equiphotel and Imbibe)
4. `/client-successes` — Imbibe top section reads "Ade helped…"; Imbibe column 2 body reads "…Ade scoped and implemented the Grip matchmaking app…"
5. `/client-successes` — footer CTA closer reads "Ade would welcome the conversation"
6. `/client-successes/incosmetics-global` — top section reads "Ade identified…"; Column 2 header reads "What Ade did:"; narrative Para 3 reads "…Ade trialled NFC-enabled devices…"; footer CTA reads "Ade would welcome the conversation"
7. `/client-successes/rx-global-research` — top section reads "Ade led a multi-country research programme…"; Column 2 header reads "What Ade did:"; narrative Para 2 reads "…Ade selected The Sound HQ…"; narrative Para 6 reads "…Ade delivered a programme of 19 workshops…"; footer CTA reads "Ade would welcome the conversation"
8. `/client-successes/clarion-ai-assistant` — unchanged; renders exactly as before
9. Client testimonials (Sonja Van Praag on Equiphotel and Imbibe pages, Chet Burchett on RX Global page, TSNN citation on Clarion page, Mark Maydon on homepage) — all unchanged
10. `/services`, `/about`, `/insights`, `/insights/navigation`, `/insights/data` — no changes, render exactly as before
11. `npm run build` — completes without errors (content-only change, no structural risk)
12. Scroll reveal animations, buttons, links, layouts — all unchanged

---

### Notes for future case studies

When building new case study pages:

- If Ade was personally recruited → third person throughout (Rule 2, 4, 5)
- If Ade brought in others to pitch a team → "we" voice (Ade will flag this)
- Card summary on the index page → always voice-neutral (Rule 3)
- Signed client copy and client testimonials → always verbatim
