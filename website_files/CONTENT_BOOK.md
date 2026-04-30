# CONTENT_BOOK.md — Book a consultation page

This is the content spec for `/book`, a dedicated page that acts as the single destination for every booking CTA across the site (with the exception that the page itself contains the outbound link to the Google Calendar booking URL).

The purpose of this page is to introduce light, intentional friction between a CTA click and the Google Calendar booking UI — setting expectations for what the call covers, reassuring the prospect, and giving direct traffic a clean landing page. It also future-proofs the site for a possible future swap to an embedded booking provider: a single page to update rather than every CTA on the site.

> **Revision note:** This file supersedes the original `CONTENT_BOOK.md` after the layout and typography corrections agreed in `TASKS_ADDENDUM_BOOK_PAGE_FIX.md` (Task 18). The structural shape changed from a single-column body page to a two-column hero-led page; the reassurance line was promoted from a 13px italic paragraph to a 28px H3; the cover section's left edge was aligned with the hero text column; and the decorative cover-section H2 was dropped. Where any other documentation refers to the original spec, this file is the source of truth.

---

## Page metadata

- **URL:** `/book`
- **Page title (browser tab / SEO):** Book a consultation — Allenby Advisory
- **Meta description:** Book a free 30-minute consultation with Allenby Advisory. No pitch, no pressure — just a conversation about your event technology, audience, or digital challenge.
- **Indexing:** Indexed (no `noindex`)
- **OG image:** Site default (`og-default.png`)

---

## Page structure

Top to bottom:

1. **Hero** — two-column grid (text left, image right), full hero pattern matching the homepage
2. **What we'll cover** — full-width section with eyebrow column left, three numbered items right
3. **Closing CTA strip** — H3 reassurance line, primary CTA button, email fallback line, all centred as one composed block

No breadcrumb. No dark footer CTA section (the page itself is the CTA destination — a closing CTA on the page that points to a booking page would be circular).

---

## Section 1 — Hero

**Layout:** Two-column grid mirroring the homepage hero pattern from `TASKS_ADDENDUM_HERO_IMAGE.md`. Text left, image right. `--offwhite` background on the text side; the image side carries the duotone-treated photograph with overlays that fade into `--offwhite` at the column boundary.

```css
.book-hero {
  position: relative;
  display: grid;
  grid-template-columns: 1fr 1fr;
  min-height: 540px;
  overflow: hidden;
  border-bottom: 0.5px solid var(--lightgrey);
}

.book-hero-text {
  position: relative;
  z-index: 2;
  padding: var(--space-2xl) var(--space-lg);
  display: flex;
  flex-direction: column;
  justify-content: center;
  max-width: 640px;
}
```

### Left column content (in order)

**Eyebrow:** Book a consultation
*(SectionLabel component; Archivo 11px, tracked, uppercase, `--midgrey`; 28px margin-bottom)*

**H1:** Thirty minutes. Genuinely useful.
*(Archivo Condensed 700, page H1 size per `BRAND.md` Section 2; line break between sentences; 28px margin-bottom)*

**Intro paragraph** (max-width 480px, body style; 36px margin-bottom):

The free consultation is designed to be useful whether or not we end up working together. Most people come with a specific question or a decision they're trying to make, and leave with a clearer view of their options.

**CTA row** (flex row, gap 24px, vertically centred):

- **Primary button:** `Book your free consultation` → href: `https://calendar.app.google/kscewyXr9JDFXDYK8`, `external={true}`
- **Inline email line** (Archivo 11px, tracked, uppercase, `--midgrey`; email link in `--accent`):
  Or email Ade directly *("Ade directly" is the `mailto:ade@allenby-advisory.com` link)*

### Right column — image with duotone treatment

**Image source:** `book_a_meeting_image.png` (from `website_images/`, copied into `src/assets/`)

The image renders via Astro's `<Image>` component with three stacked CSS overlays applied identically to the homepage hero per `TASKS_ADDENDUM_HERO_IMAGE.md`:

1. **Charcoal multiply layer** — opacity 0.55, deepens shadows toward `--charcoal` rather than neutral black
2. **Accent colour-blend layer** — opacity 0.15–0.18, applies a subtle accent-blue tonal shift
3. **Offwhite linear gradient fade** — `0% → 18% → 55%` from `--offwhite` opaque to transparent, ensuring the text column sits on a clean offwhite background

The image is decorative — `alt=""` and `aria-hidden="true"` on the wrapper. `loading="eager"` because it's above the fold.

The duotone tuning values (`0.55` multiply, `0.15` accent, `0%→18%→55%` fade) match the homepage and may be adjusted post-implementation to taste — these are reviewable defaults, not fixed values.

### Mobile (≤768px)

Image hides (Option A from the homepage hero). The hero stacks to text-only on `--offwhite`. CTA row wraps if needed: button on first line, email line on second.

### Animation

The hero H1 uses the slide-up animation via `transition:animate` per the homepage pattern. The hero image fades in 0.15s after the H1 starts. Apply the same `prefers-reduced-motion` rule as the homepage hero — the image appears instantly when reduced motion is requested.

---

## Section 2 — What we'll cover

**Layout:** Standard site section — `var(--space-2xl) var(--space-lg)` padding (72px top/bottom, 40px left/right), `--offwhite` background, `border-bottom: 0.5px solid var(--lightgrey)`. **No centred max-width container.** The section runs edge-to-edge with consistent 40px side padding so the eyebrow's left edge aligns vertically with the hero eyebrow above.

Inside the section, a two-column grid:

```css
.book-cover-inner {
  display: grid;
  grid-template-columns: 280px 1fr;
  gap: 80px;
  align-items: start;
}
```

### Left column — eyebrow only

**Eyebrow:** What we'll cover
*(Archivo 11px, tracked, uppercase, `--midgrey`)*

No H2. The eyebrow alone introduces the list. This gives the closing H3 in Section 3 clear secondary-heading hierarchy after the H1.

### Right column — numbered list

Styled identically to the About page "Flexible by design" engagement list:

- Each item is a `64px 1fr` row grid with 24px column gap
- Number column: Archivo Condensed 700, 28px, `--lightgrey` (decorative — not a functional list number)
- Label: Archivo 700, 11px, tracked, uppercase, `--charcoal`, 8px margin-bottom
- Description: body style (15px, line-height 1.65, `--body`)
- Each item: padding 22px 0, `border-bottom: 0.5px solid var(--lightgrey)` except the last
- First item: `padding-top: 0`

#### Item 1
- **Number:** 01
- **Label:** Where you are now
- **Description:** The current state of your event tech, audience experience, or digital capability — and the gaps you're feeling.

#### Item 2
- **Number:** 02
- **Label:** What you're trying to achieve
- **Description:** The outcome you're working toward — whether that's a platform decision, a delivery problem, or building internal capability.

#### Item 3
- **Number:** 03
- **Label:** Where we might help (or not)
- **Description:** An honest view of where we could add value — and where you're better served by another route. If we're not the right fit, we'll say so.

### Mobile (≤768px)

Single column. Eyebrow stacks above the list. Standard mobile section padding `48px 20px` per `BRAND.md` Section 15.

---

## Section 3 — Closing CTA strip

**Layout:** Centred block, `var(--space-2xl) var(--space-lg)` section padding, `--offwhite` background. The H3, button, and email line compose as one block — no section break between them, no internal hairline border.

**H3:**

```css
.book-closing-h3 {
  font-family: 'Archivo Condensed', sans-serif;
  font-weight: 700;
  font-size: 28px;
  line-height: 1.2;
  letter-spacing: 0.01em;
  color: var(--charcoal);
  margin-bottom: 32px;
}
```

Use a real `<h3>` element (not styled `<p>`) for semantic correctness.

**Copy:** No pitch, no pressure — just a conversation.

**Primary button** (centred, 20px margin-bottom):
- Label: Book your free consultation
- href: `https://calendar.app.google/kscewyXr9JDFXDYK8`
- `external={true}` (opens in new tab)

**Email fallback line:**
- Style: Archivo 11px, tracked, uppercase, `--midgrey`; email link in `--accent`
- Copy: Or email Ade directly: ade@allenby-advisory.com

The whole block is `text-align: center`. Vertical rhythm: H3 → 32px gap → button → 20px gap → email line.

### Mobile (≤768px)

Same composition, reduced section padding `48px 20px`. H3 size reduces to 22px.

---

## Heading hierarchy

The page contains exactly one H1 (in the hero), zero H2s, and one H3 (the closing reassurance line). H1 → H3 with no H2 is intentional — H3 acts as the next-most-important heading after H1, and no H2 is required by spec.

---

## Animation

Apply `class="reveal"` to:
- The hero text block (eyebrow + H1 + intro + CTA row, as one group)
- Each numbered item in the cover section (staggered, 0s / 0.1s / 0.2s delays)
- The closing block (H3 + button + email line, as one group)

The hero image animates via the duotone fade-in pattern from the homepage; `reveal` is not applied to it.

---

## Voice notes

- The page uses the default site voice ("we") per `TASKS_ADDENDUM_VOICE_AUDIT.md`. This is not a case study page.
- The email fallback lines (both in the hero CTA row and at the foot of the page) use "Ade" deliberately — the email goes to him personally, matching the homepage `#contact` pattern.
