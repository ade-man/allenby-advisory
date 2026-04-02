# TASKS_ADDENDUM_BOOKING.md — Google Calendar Booking Integration

This task replaces the placeholder `/#contact` booking links with a live Google Calendar booking page. It can be completed at any point after Task 10 (final QA).

---

## Task 12 — Google Calendar booking integration

**Goal:** Replace all placeholder booking button links with the live Google Calendar booking URL, and update the nav CTA. The booking page opens in a new tab — no embed, no iframe, no Google scripts.

**Booking URL:** `https://calendar.app.google/kscewyXr9JDFXDYK8`

**Read first:** `BRAND.md` Section 6 (Button component). Review all content files to understand the current placeholder pattern.

---

### Approach

We are **not** embedding Google's booking UI into the site. Google's inline embed and popup button both inject their own styles (Material Design, rounded corners, Google fonts) which conflict with the brand's square-cornered, Archivo-based design system. The booking page cannot be visually customised.

Instead, all existing `Button.astro` instances that currently link to `/#contact` or `#contact` or `#` will link directly to the Google Calendar booking page, opening in a new tab. The user clicks a branded button, lands on the booking page — clean and simple.

The one exception is the **homepage footer CTA section** (id="contact"). This section remains as an anchor destination because the nav CTA and hero ghost button scroll to it. The section's own booking button then links out to the Google Calendar page. This preserves the two-step flow: scroll to the CTA context → click through to book.

---

### Steps

**1. Update `src/components/Button.astro` to support external links:**

Add an optional `external` prop (boolean, default `false`). When `true`, the rendered `<a>` tag should include `target="_blank"` and `rel="noopener noreferrer"`.

```astro
---
interface Props {
  label: string;
  href: string;
  variant?: 'primary' | 'ghost' | 'light';
  external?: boolean;
}

const { label, href, variant = 'primary', external = false } = Astro.props;
---

<a
  href={href}
  class={`btn btn-${variant}`}
  {...(external ? { target: '_blank', rel: 'noopener noreferrer' } : {})}
>
  {label}
</a>
```

If `Button.astro` already handles `target="_blank"` via a different mechanism, adapt accordingly — the key requirement is that external links open in a new tab.

---

**2. Update `src/components/Nav.astro`:**

Change the nav CTA button href from `/#contact` to `https://calendar.app.google/kscewyXr9JDFXDYK8`. Add `target="_blank"` and `rel="noopener noreferrer"` to the CTA anchor. The label remains "Book a consultation".

---

**3. Update each page — button by button:**

Work through every page file listed below. For each booking button, update the `href` to `https://calendar.app.google/kscewyXr9JDFXDYK8` and add `external={true}` (or `external`).

**Do not change** the `/#contact` href on the homepage hero CTA or the homepage hero ghost button — these scroll the user to the footer CTA section, which is the intended behaviour.

#### `src/pages/index.astro` (Homepage)

| Button | Current href | New href | External? | Notes |
|---|---|---|---|---|
| Hero primary CTA ("Book a free 30-minute consultation") | `#contact` | `#contact` | No | **Keep as-is** — scrolls to footer CTA section |
| Hero ghost CTA ("See our work") | `/client-successes` | `/client-successes` | No | **Keep as-is** — not a booking link |
| Footer CTA button ("Book your free consultation") | `#` or `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes | This is the actual booking action |

#### `src/pages/services.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Service 1 — "Let's talk" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |
| Service 2 — "Tell us about your project" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |
| Service 3 — "Let's explore this" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |
| Footer CTA — "Book a free consultation" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |

#### `src/pages/client-successes.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Equiphotel — "Get in touch about a similar project" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |
| Imbibe — "Get in touch about a similar project" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |
| Footer CTA — "Book a free 30-minute call" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |

#### `src/pages/client-successes/incosmetics-global.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Top section — "Get in touch about a similar project" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |
| Footer CTA — "Book a free 30-minute call" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |

#### `src/pages/client-successes/rx-global-research.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Top section — "Get in touch about a similar project" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |
| Footer CTA — "Book a free 30-minute call" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |

#### `src/pages/about.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Flexible section — "Book a free call" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |
| Footer CTA — "Book a free consultation" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |

#### `src/pages/insights.astro`

| Button | Current href | New href | External? |
|---|---|---|---|
| Footer CTA — "Book a free 30-minute call" | `/#contact` | `https://calendar.app.google/kscewyXr9JDFXDYK8` | Yes |

---

**4. Homepage footer CTA section — keep the anchor, update copy and button:**

The `<section id="contact">` on the homepage must remain as an anchor target. Update the button href to the Google Calendar URL with `external={true}`. The email line (`ade@allenby-advisory.com`) remains unchanged.

**Replace the body copy in this section.** The H2 stays the same. Replace the existing single body paragraph with the following two paragraphs:

**H2 (unchanged):** Not sure whether you need help right now?

**Body paragraph 1:** The free 30-minute consultation is designed to be genuinely useful — whether or not we end up working together. Most people come with a specific question or a decision they're trying to make, and leave with a clearer view of their options.

**Body paragraph 2:** We'll typically cover where you are now, what you're trying to achieve, and where the gaps are — whether that's technology selection, adoption, internal capability or something else entirely. If there's a way we can help, we'll say so. If there isn't, we'll tell you that too.

Both paragraphs use the dark section body style: 15px, line-height 1.65, color `#c8c6c2`, max-width 560px. Add `margin-bottom: 12px` between the two paragraphs.

**Button (light variant, unchanged label):** Book your free consultation → href: `https://calendar.app.google/kscewyXr9JDFXDYK8`, `external={true}`

**Email line (unchanged):** Or email Ade directly: ade@allenby-advisory.com

---

**5. No Google scripts or embeds:**

Do **not** add any of the following:
- `calendar.google.com/calendar/scheduling-button-script.js`
- `calendar.google.com/calendar/scheduling-button-script.css`
- Any `<iframe>` pointing to Google Calendar
- Any Google-generated embed code

The integration is a simple link. Nothing more.

---

### Verification

1. **Nav CTA:** Click "Book a consultation" in the nav on every page — opens the Google Calendar booking page in a new tab
2. **Homepage hero CTA:** Click "Book a free 30-minute consultation" — scrolls smoothly to the `#contact` section (does NOT open a new tab)
3. **Homepage footer CTA button:** Click "Book your free consultation" — opens the Google Calendar booking page in a new tab
4. **Services page:** Click all three service buttons ("Let's talk", "Tell us about your project", "Let's explore this") and the footer CTA — all open the booking page in a new tab
5. **Client successes pages:** Click every "Get in touch about a similar project" button and every footer CTA — all open the booking page in a new tab
6. **About page:** Click "Book a free call" and the footer CTA — both open the booking page in a new tab
7. **Insights page:** Click the footer CTA — opens the booking page in a new tab
8. **Email link:** Confirm `ade@allenby-advisory.com` on the homepage footer CTA still opens the user's email client (unchanged)
9. **Footer CTA copy:** Confirm the homepage `#contact` section shows two body paragraphs (starting "The free 30-minute consultation…" and "We'll typically cover…"), not the old single paragraph
10. **No visual changes:** No new UI elements, scripts, or styles have been added. The only changes are link destinations, the `target="_blank"` attribute on external booking links, and the updated footer CTA copy on the homepage
11. **Build check:** Run `npm run build` — no errors
