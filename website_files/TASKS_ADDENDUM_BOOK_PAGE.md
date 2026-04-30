# TASKS_ADDENDUM_BOOK_PAGE.md — Dedicated /book consultation page

This addendum supersedes the link destinations established in `TASKS_ADDENDUM_BOOKING.md`. It can be completed at any point — there are no dependencies on in-flight tasks. It is purely a route-and-copy change: a new page is added, and every existing booking CTA on the site is repointed from the Google Calendar URL to the new internal `/book` page.

---

## Task 17 — Dedicated /book consultation page

**Goal:** Add a new `/book` page that acts as the single destination for every booking CTA on the site. The page introduces light, intentional friction between a CTA click and the Google Calendar booking UI — setting expectations and reassuring the prospect. Repoint every existing booking CTA (currently linking to the Google Calendar URL) to `/book` as an internal link. Only the booking button on `/book` itself opens the Google Calendar URL externally.

**Read first:**
- `CONTENT_BOOK.md` — full content and layout spec for the new page
- `BRAND.md` Sections 1, 2, 6, 7 (palette, typography, Button, SectionLabel)
- `CONTENT_ABOUT.md` — the "Flexible by design" engagement list is the visual reference for the numbered list on `/book`
- `TASKS_ADDENDUM_BOOKING.md` — establishes the existing button pattern this task replaces

---

### Approach

`/book` becomes the universal handshake page. Every booking button on the site links to `/book` as a same-tab internal navigation. Only the page itself contains the outbound link to `https://calendar.app.google/kscewyXr9JDFXDYK8` (opening in a new tab).

The homepage `#contact` section is preserved in place — its body copy remains unchanged. The CTA button within it is repointed to `/book` like every other CTA.

This pattern future-proofs the site: if the booking provider changes (e.g. to one that supports a clean inline embed), only `/book` needs updating.

---

### Steps

**1. Create `src/pages/book.astro`:**

Follow `CONTENT_BOOK.md` in full. The page reuses existing components (`Nav`, `Footer`, `Button`, `SectionLabel`) — no new components are required. The numbered list reuses the same CSS pattern as the About page "Flexible by design" engagement list.

Page metadata:
- Title: `Book a consultation — Allenby Advisory`
- Meta description: `Book a free 30-minute consultation with Allenby Advisory. No pitch, no pressure — just a conversation about your event technology, audience, or digital challenge.`
- OG image: site default (`og-default.png`)
- Indexed (no `noindex`)

The page does NOT include a dark footer CTA section. The booking action sits inline at the bottom of the content on `--offwhite` background.

---

**2. Repoint every booking CTA across the site to `/book`:**

For every button listed below, change the `href` to `/book` and **remove** the `external` prop (or set it to `false`). These are now internal navigations — same tab, no `target="_blank"`.

The label on each button stays exactly as-is.

#### `src/components/Nav.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Nav CTA — "Book a consultation" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |

Remove `target="_blank"` and `rel="noopener noreferrer"` from this anchor.

#### `src/pages/index.astro` (Homepage)

| Button | Current href | New href | External? | Notes |
|---|---|---|---|---|
| Hero primary CTA — "Book a free 30-minute consultation" | `#contact` | `/book` | No | Was scrolling to `#contact`; now navigates to `/book` |
| Hero ghost CTA — "See our work" | `/client-successes` | `/client-successes` | No | **Keep as-is** — not a booking link |
| Footer `#contact` section button — "Book your free consultation" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No | Was external; now internal |

The `<section id="contact">` element on the homepage **stays in place** with all its existing body copy unchanged. Only the button's `href` and `external` prop are updated.

#### `src/pages/services.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Service 1 — "Let's talk" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |
| Service 2 — "Tell us about your project" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |
| Service 3 — "Let's explore this" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |
| Footer CTA — "Book a free consultation" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |

#### `src/pages/client-successes.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Equiphotel — "Get in touch about a similar project" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |
| Imbibe — "Get in touch about a similar project" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |
| Footer CTA — "Book a free 30-minute call" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |

#### `src/pages/client-successes/incosmetics-global.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Top section — "Get in touch about a similar project" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |
| Footer CTA — "Book a free 30-minute call" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |

#### `src/pages/client-successes/rx-global-research.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Top section — "Get in touch about a similar project" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |
| Footer CTA — "Book a free 30-minute call" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |

#### `src/pages/client-successes/global-banking-markets.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Top section — "Get in touch about a similar project" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |
| Footer CTA — "Book a free 30-minute call" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |

#### `src/pages/client-successes/clarion-ai-assistant.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Top section — "Get in touch about a similar project" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |
| Footer CTA — "Book a free 30-minute call" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |

#### `src/pages/about.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Flexible section — "Book a free call" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |
| Footer CTA — "Book a free consultation" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |

#### `src/pages/insights.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Footer CTA — "Book a free 30-minute call" | `https://calendar.app.google/kscewyXr9JDFXDYK8` | `/book` | No |

#### Equiphotel and Imbibe dedicated case study pages

If/when these pages exist (per Task 15 — Portfolio restructure), apply the same pattern: every booking CTA on those pages links to `/book` as an internal navigation. Note this in the Task 15 verification rather than implementing speculatively here.

---

**3. The only outbound booking link on the site is on `/book` itself:**

The CTA button on `/book` (label: "Book your free consultation") is the single button across the entire site that links directly to the Google Calendar URL with `external={true}`. Every other booking CTA goes through `/book`.

---

**4. Do not add `/book` to the main nav as a separate link:**

The nav CTA "Book a consultation" already serves this purpose. Adding `/book` as a separate nav item would be redundant clutter.

---

**5. No Google scripts or embeds:**

As established in `TASKS_ADDENDUM_BOOKING.md` — the integration remains a simple link. No `calendar.google.com/calendar/scheduling-button-script.js`, no iframe, no popup script.

---

### Verification

1. **`/book` page renders:** Navigate to `/book` directly. Page loads with header, three numbered items, reassurance line, and centred CTA button.
2. **`/book` CTA opens Google Calendar in a new tab:** Click "Book your free consultation" on `/book` — Google Calendar opens in a new tab.
3. **`/book` email link works:** Clicking `ade@allenby-advisory.com` opens the user's email client.
4. **Page metadata:** View source on `/book` — `<title>` is `Book a consultation — Allenby Advisory`, meta description matches the spec, no `noindex`.
5. **Nav CTA:** Click "Book a consultation" in the nav on every page — navigates to `/book` in the **same tab** (no new tab).
6. **Homepage hero CTA:** Click "Book a free 30-minute consultation" in the hero — navigates to `/book` in the same tab. Confirm it no longer scrolls to `#contact`.
7. **Homepage hero ghost CTA:** Click "See our work" — still navigates to `/client-successes`. Unchanged.
8. **Homepage `#contact` section:** Confirm the section is still in place with its existing body copy unchanged. Click "Book your free consultation" within it — navigates to `/book` in the same tab.
9. **Services page:** Click all three service buttons and the footer CTA — all navigate to `/book` in the same tab.
10. **Client successes (index page):** Click both inline "Get in touch about a similar project" buttons (Equiphotel, Imbibe) and the footer CTA — all navigate to `/book` in the same tab.
11. **Each case study page** (Incosmetics, RX, GBM, Clarion AI): Click the top-section CTA and the footer CTA — both navigate to `/book` in the same tab.
12. **About page:** Click "Book a free call" and the footer CTA — both navigate to `/book` in the same tab.
13. **Insights page:** Click the footer CTA — navigates to `/book` in the same tab.
14. **No site-wide external booking link except on `/book`:** Search the codebase for `calendar.app.google/kscewyXr9JDFXDYK8` — it should appear only in `src/pages/book.astro` (and unchanged in the verification scripts of any historical task files, which is fine — those are documentation).
15. **No new nav item:** Confirm the main nav still shows only the original links plus the CTA — no separate "Book" link added.
16. **Animation reveal:** On `/book`, scroll/refresh — page sections fade in via the `reveal` pattern as on other pages.
17. **Mobile layout:** On a narrow viewport, the numbered list stacks cleanly (number above label/description if needed), the CTA button remains tappable, and the email fallback line wraps gracefully.
18. **Build check:** Run `npm run build` — no errors, no broken links.

---

## Items to confirm before implementation

- **`/book` page background:** The spec calls for `--offwhite` throughout (no dark section). If Cline judges that visual rhythm needs a dark band somewhere, raise it before implementing — do not add one speculatively. The intent is a deliberately quiet, single-purpose page.
- **Numbered list mobile layout:** Match the About page's responsive behaviour for the engagement list. If the About page stacks number-above-content at narrow widths, do the same here.
