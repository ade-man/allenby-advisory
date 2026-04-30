# TASKS_ADDENDUM_BOOK_PAGE_FIX.md — /book page layout and typography corrections

This addendum corrects four issues in the live `/book` page implementation. It depends on Task 17 (`TASKS_ADDENDUM_BOOK_PAGE.md`) being complete, which it is. It also amends the original `CONTENT_BOOK.md` content spec — the changes here supersede the relevant sections of that file.

The four corrections:

1. The page is rendering as body content with a narrow left-anchored column, leaving the right two-thirds of the viewport empty. It should be a hero-led page with a two-column hero (text left, image right) matching the homepage hero pattern.
2. The reassurance line ("No pitch, no pressure — just a conversation.") is rendered at undersized 13px italic text — both because the original spec specified 13px (a fabrication that doesn't match any other supporting text on the site), and because it's structurally separated from the CTA by a section break. It should be promoted to an H3 sitting directly above the CTA as one composed block.
3. The "What we'll cover" section uses a centred max-width container, causing its left edge to misalign with the hero text column above. It should follow the standard site pattern (`var(--space-2xl) var(--space-lg)` section padding, no centred container) so its left edge aligns with the hero text.
4. The decorative H2 ("Three things, thirty minutes.") in the cover section is dropped. The eyebrow alone introduces the list, which gives the closing H3 clear secondary-heading hierarchy after the H1.

Cline should also add the `book_a_meeting_image.png` asset to the hero, treated with the same duotone overlay pattern as the homepage hero (per `TASKS_ADDENDUM_HERO_IMAGE.md`).

---

## Task 18 — /book page layout and typography corrections

**Goal:** Restructure `src/pages/book.astro` so the page reads as a hero-led page rather than narrow body content, add the `book_a_meeting_image.png` image to the hero with the homepage duotone treatment, promote the reassurance line to an H3 with proper composition next to the CTA, align the cover-section left edge with the hero text column, and drop the decorative H2 from the cover section.

**Read first:**
- `BRAND.md` Sections 1, 2, 3, 6, 7 (palette, typography, spacing, Button, SectionLabel)
- `TASKS_ADDENDUM_HERO_IMAGE.md` — the duotone overlay pattern for the hero image is reused here
- `CONTENT_ABOUT.md` — the "Flexible by design" engagement list is the visual reference for the numbered list
- The current live `src/pages/book.astro` to understand what's being changed
- This file in full before changing anything; the four corrections are interdependent

---

### Image asset

**Source file:** `website_images/book_a_meeting_image.png`

Add this image to the project as follows:

1. Copy `website_images/book_a_meeting_image.png` to `src/assets/book_a_meeting_image.png` so Astro's image optimisation pipeline picks it up.
2. Use Astro's `<Image>` component from `astro:assets` to render it (matches the homepage hero pattern from `TASKS_ADDENDUM_HERO_IMAGE.md`).

---

### Page structure (revised)

Top to bottom:

1. **Hero** — two-column grid, text left, image right (was: single-column body header)
2. **What we'll cover** — full-width section with `280px 1fr` internal grid, eyebrow column left, numbered list right (was: centred max-width container with H2)
3. **Closing CTA strip** — H3 reassurance line + button + email line as one composed centred block (was: italic 13px line floating above a separate CTA section)

No breadcrumb. No dark footer CTA section.

---

### Section 1 — Hero (replaces existing top section)

**Layout:** Two-column grid, mirroring the homepage hero markup pattern from `TASKS_ADDENDUM_HERO_IMAGE.md`.

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

**Left column content** (in order):

1. **Eyebrow:** `Book a consultation` (SectionLabel component, 28px margin-bottom)
2. **H1:** `Thirty minutes. Genuinely useful.` (Archivo Condensed 700, page H1 size per `BRAND.md`; line break between sentences)
3. **Intro paragraph** (max-width 480px, body style, 36px margin-bottom):
   *The free consultation is designed to be useful whether or not we end up working together. Most people come with a specific question or a decision they're trying to make, and leave with a clearer view of their options.*
4. **CTA row** — flex row, gap 24px, vertically centred:
   - **Primary button:** `Book your free consultation` → `https://calendar.app.google/kscewyXr9JDFXDYK8`, `external={true}`
   - **Inline email line** (Archivo 11px, tracked, uppercase, `--midgrey`; email link in `--accent`):
     `Or email Ade directly` (with "Ade directly" as a `mailto:ade@allenby-advisory.com` link)

**Right column** — image with three-layer overlay treatment:

```astro
---
import { Image } from 'astro:assets';
import bookImage from '../assets/book_a_meeting_image.png';
---

<div class="book-hero-image" aria-hidden="true">
  <Image
    src={bookImage}
    alt=""
    widths={[720, 1080, 1440]}
    sizes="(max-width: 768px) 100vw, 50vw"
    loading="eager"
    class="book-hero-image-photo"
  />
  <div class="book-hero-image-overlay-multiply"></div>
  <div class="book-hero-image-overlay-accent"></div>
  <div class="book-hero-image-overlay-fade"></div>
</div>
```

CSS for the image and overlays — reuse the homepage pattern from `TASKS_ADDENDUM_HERO_IMAGE.md` exactly (charcoal multiply at 0.55, accent colour-blend at 0.15–0.18, offwhite linear gradient fade `0%→18%→55%`). The values can be tuned post-implementation; start from those defaults.

Apply the same `prefers-reduced-motion` rule for the fade-in animation as on the homepage.

**Mobile (≤768px):** Image hides (Option A from the homepage hero). The hero stacks to text-only on `--offwhite`. CTA row should wrap if needed (button on first line, email line on second).

---

### Section 2 — What we'll cover (revised)

**Layout:** Standard site section — `var(--space-2xl) var(--space-lg)` padding, `--offwhite` background, `border-bottom: 0.5px solid var(--lightgrey)`. **No centred max-width container.** The section runs edge-to-edge with consistent 40px side padding; the eyebrow's left edge sits at 40px, vertically aligned with the hero eyebrow above.

Inside the section, a two-column grid:

```css
.book-cover-inner {
  display: grid;
  grid-template-columns: 280px 1fr;
  gap: 80px;
  align-items: start;
}
```

**Left column:** Just the eyebrow `What we'll cover` — Archivo 11px, tracked, uppercase, `--midgrey`. **The decorative H2 is dropped.** No "Three things, thirty minutes." H2.

**Right column:** The numbered list (three items), styled identically to the About page "Flexible by design" engagement list:

- Each item is a `64px 1fr` row grid with 24px column gap
- Number column: Archivo Condensed 700, 28px, `--lightgrey`
- Label: Archivo 700, 11px, tracked, uppercase, `--charcoal`, 8px margin-bottom
- Description: body style (15px, line-height 1.65, `--body`)
- Each item: padding 22px 0, `border-bottom: 0.5px solid var(--lightgrey)` except the last
- First item: `padding-top: 0`

Item content (unchanged from `CONTENT_BOOK.md`):

| # | Label | Description |
|---|---|---|
| 01 | Where you are now | The current state of your event tech, audience experience, or digital capability — and the gaps you're feeling. |
| 02 | What you're trying to achieve | The outcome you're working toward — whether that's a platform decision, a delivery problem, or building internal capability. |
| 03 | Where we might help (or not) | An honest view of where we could add value — and where you're better served by another route. If we're not the right fit, we'll say so. |

**Mobile (≤768px):** Single column. Eyebrow stacks above the list. Standard mobile section padding `48px 20px` per `BRAND.md` Section 15.

---

### Section 3 — Closing CTA strip (revised)

**Layout:** Centred block, `var(--space-2xl) var(--space-lg)` section padding, `--offwhite` background. No section border between the H3 and the CTA — the H3, button, and email line compose as one block.

**H3 (promoted from `<p>`):**
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

**Copy (unchanged):** No pitch, no pressure — just a conversation.

**Primary button** (centred, 20px margin-bottom): `Book your free consultation` → `https://calendar.app.google/kscewyXr9JDFXDYK8`, `external={true}`

**Email fallback line:** Archivo 11px, tracked, uppercase, `--midgrey`; email link in `--accent`. Copy: `Or email Ade directly: ade@allenby-advisory.com`

The whole block is `text-align: center`. Vertical rhythm: H3 → 32px gap → button → 20px gap → email line.

**Mobile (≤768px):** Same composition, reduced section padding `48px 20px`. H3 size reduces to 22px.

---

### Animation

Apply `class="reveal"` to:
- The hero text block (eyebrow + H1 + intro + CTA row, as one group)
- The hero image wrapper (already animates via the duotone fade-in pattern from the homepage; `reveal` not needed here)
- Each numbered item in the cover section (staggered, 0s / 0.1s / 0.2s delays)
- The closing block (H3 + button + email line, as one group)

The hero H1 also gets the slide-up animation via `transition:animate` per the homepage pattern.

---

### What's not changing

- The page's URL (`/book`), metadata (title, description, OG image, indexing), nav inclusion (none — nav CTA is sufficient), and link destinations from elsewhere in the site (all booking CTAs continue to point to `/book`).
- The Google Calendar booking URL (`https://calendar.app.google/kscewyXr9JDFXDYK8`) is still the only outbound booking link, called once on this page.
- No new components are introduced. Existing `Nav`, `Footer`, `Button`, and `SectionLabel` components are reused.

---

### Verification

1. **Hero layout:** On desktop, the hero is a two-column grid with text occupying the left half and the duotone-treated `book_a_meeting_image.png` on the right. The image fades smoothly into `--offwhite` behind the text — no hard seam.
2. **Hero text:** Eyebrow, H1 ("Thirty minutes. Genuinely useful." across two lines), intro paragraph, primary CTA button, and inline email link all render in the left column on `--offwhite`.
3. **Hero CTA:** Click "Book your free consultation" in the hero — opens Google Calendar in a new tab.
4. **Hero email link:** Click "Ade directly" inline — opens email client with `ade@allenby-advisory.com` populated.
5. **Image treatment:** The hero image reads as black-and-white with a subtle accent-blue tonal cast (not pure greyscale). Shadow areas should feel like they belong with `--charcoal`, not neutral black.
6. **Section alignment:** The "WHAT WE'LL COVER" eyebrow sits at the same horizontal position as the "BOOK A CONSULTATION" hero eyebrow above — both at 40px from the left edge. The two left edges visibly align when scanned vertically.
7. **No H2 in cover section:** The text "Three things, thirty minutes." does not appear anywhere on the page. The eyebrow alone introduces the numbered list.
8. **Numbered list styling:** Visually consistent with the About page engagement list — large `--lightgrey` number, ALL CAPS label, body-style description, hairline separator between items.
9. **Closing H3:** "No pitch, no pressure — just a conversation." renders at H3 size (28px Archivo Condensed 700, `--charcoal`, sentence case) — matching the size of card/tile H3s elsewhere on the site. Not italic. Not body-text size.
10. **Closing block composition:** No section border between the H3 and the button. H3 → 32px gap → button → 20px gap → email line read as one centred composed block.
11. **Closing CTA:** Click "Book your free consultation" at the foot of the page — opens Google Calendar in a new tab.
12. **Closing email link:** Click `ade@allenby-advisory.com` at the foot — opens email client.
13. **Mobile (≤768px):** Hero stacks to text-only (image hidden, Option A). Cover section eyebrow stacks above the numbered list. Closing block remains centred. No horizontal overflow.
14. **Reduced motion:** With `prefers-reduced-motion: reduce` set, the hero image appears instantly without fade-in.
15. **Heading hierarchy:** Page contains exactly one H1 (the hero), zero H2s, and one H3 (the closing line). No orphan headings, no skipped levels.
16. **Build check:** `npm run build` completes without errors. No broken image references. The optimised hero image renders in the correct format (WebP with fallback).
17. **No regressions:** Every other booking CTA across the site still navigates to `/book` in the same tab (per Task 17). The nav, homepage, services page, all case study pages, about, and insights are visually unchanged.

---

## Items to confirm before implementation

- **Image dimensions and crop:** `book_a_meeting_image.png` should ideally be at least 1440px wide on the long edge to render crisply on retina displays at the right-half hero size. If the source image is smaller than that, raise it before implementing — do not upscale. If it's portrait orientation, the `object-fit: cover` will crop top and bottom, so confirm the meaningful subject is roughly centre-frame vertically.
- **Mobile image behaviour:** Spec defaults to Option A (hide image on mobile). If the image is striking enough that Ade wants it visible on mobile too, switch to Option B from `TASKS_ADDENDUM_HERO_IMAGE.md` — but flag for sign-off before implementing.
- **Heading semantics:** The page now has H1 → H3 with no H2. This is acceptable for SEO and accessibility (H3 acts as the next-most-important heading after H1; no H2 is required by spec). If preferred, the closing line could be styled-as-H3 but tagged as H2 to maintain a contiguous hierarchy. Default is to use H3 as written and skip H2 entirely. Flag if a different choice is wanted.
