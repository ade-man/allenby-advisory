# TASKS_ADDENDUM_HERO_IMAGE.md — Homepage hero background image

This task adds a background image to the homepage hero section, occupying the right half of the hero with a charcoal duotone treatment and a horizontal fade into `--offwhite` at the text column. The visual effect: the photo reads as atmospheric context on the right, the text stays crisp on the left, and the image feels tonally integrated with the brand palette rather than dropped in as a generic stock photo.

This task should be completed after Task 10 (final QA) is verified, or in parallel with later content tasks — it doesn't conflict with anything else.

---

## Task 14 — Homepage hero background image

**Goal:** Add a duotone-treated background image to the homepage hero, occupying the right half with a fade to `--offwhite` at the text column. No other page is affected.

**Read first:** `CONTENT_HOME.md` (Hero section), `BRAND.md` Sections 1, 2, 3, 14 (colour palette, type, spacing, animations). Review the current `src/pages/index.astro` hero block to understand the markup being modified.

---

### Design intent

The photo is a black-and-white workshop/planning session scene — people at a whiteboard, strategic work in progress. The treatment pulls it into the Allenby Advisory palette:

- A charcoal-tinted multiply layer deepens the shadows toward `--charcoal` rather than neutral black.
- A subtle accent-blue colour blend shifts the overall tonal cast very slightly toward `--accent`, so the photo reads as "part of the design system" rather than "stock greyscale."
- A horizontal linear-gradient fade from `--offwhite` (opaque at 0%) to transparent at approximately 55% of the photo's width ensures the text column has a clean, consistent background colour.
- The hero's existing left-side text column is untouched — eyebrow, H1, body, CTAs stay exactly where they are.
- The accent word "expensive to get wrong." keeps its current `--accent` colour; no changes to the H1 markup.

---

### Image asset

**Source file:** The uploaded JPEG is `workshop-planning-session_copy.jpeg` (2048×2048, black-and-white, ~490KB).

Add the image to the project as follows:

1. Save the source file to `src/assets/hero-workshop.jpeg` (Astro's image optimisation pipeline picks it up from `src/assets/`).
2. Use Astro's `<Image>` component from `astro:assets` to render it — this gives automatic responsive sizing, WebP conversion with JPEG fallback, and lazy/eager loading control.

If the project isn't already using `astro:assets`, this is the point to start. It's built into Astro and requires no extra config for static sites.

---

### Implementation approach

The duotone effect is implemented **with CSS overlays**, not a pre-processed image. Reasoning: keeps a single image file (easier to swap, easier to tune), preserves detail in the source, uses `mix-blend-mode` which has universal support in modern browsers. A pre-processed duotone would work equally well but adds file-management overhead for no visible benefit.

The hero section gains a new right-half `<div>` containing the image and three stacked overlay divs (multiply charcoal, colour accent, fade to offwhite). The text column is unchanged.

---

### Markup changes — `src/pages/index.astro`

Locate the existing hero section. It currently looks approximately like this (the exact class names may differ — use whatever structure the page already has):

```astro
<section class="hero">
  <div class="hero-text">
    <!-- eyebrow, H1, body, CTAs -->
  </div>
</section>
```

Update it to:

```astro
---
import { Image } from 'astro:assets';
import heroWorkshop from '../assets/hero-workshop.jpeg';
// ...other imports
---

<section class="hero">
  <div class="hero-text">
    <!-- eyebrow, H1, body, CTAs — UNCHANGED -->
  </div>

  <div class="hero-image" aria-hidden="true">
    <Image
      src={heroWorkshop}
      alt=""
      widths={[720, 1080, 1440]}
      sizes="(max-width: 768px) 100vw, 50vw"
      loading="eager"
      class="hero-image-photo"
    />
    <div class="hero-image-overlay-multiply"></div>
    <div class="hero-image-overlay-accent"></div>
    <div class="hero-image-overlay-fade"></div>
  </div>
</section>
```

Notes on the markup:

- `aria-hidden="true"` on the wrapper and `alt=""` on the image are correct — this is decorative, not informational. Screen readers should skip it.
- `loading="eager"` because the hero is above the fold.
- `sizes` hints to the browser: at mobile widths the image takes full viewport width; at desktop it takes half.
- The three overlay divs stack in source order; `z-index` isn't needed because each subsequent sibling paints on top of the previous.

---

### CSS — add to `src/styles/global.css`

Add the following block at the end of `global.css`, under a comment `/* Homepage hero — background image */`:

```css
/* Homepage hero — background image */

.hero {
  position: relative;
  display: grid;
  grid-template-columns: 1fr 1fr;
  min-height: 540px;
  overflow: hidden;
}

.hero-text {
  position: relative;
  z-index: 2;
  padding: var(--space-2xl) var(--space-lg);
  /* If the existing hero already has padding/layout rules, merge — don't duplicate. */
}

.hero-image {
  position: relative;
  overflow: hidden;
}

.hero-image-photo {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}

/* Layer 1 — charcoal multiply to deepen shadows into brand charcoal */
.hero-image-overlay-multiply {
  position: absolute;
  inset: 0;
  background: var(--charcoal);
  mix-blend-mode: multiply;
  opacity: 0.55;
  pointer-events: none;
}

/* Layer 2 — subtle accent colour shift */
.hero-image-overlay-accent {
  position: absolute;
  inset: 0;
  background: var(--accent);
  mix-blend-mode: color;
  opacity: 0.15;
  pointer-events: none;
}

/* Layer 3 — horizontal fade into offwhite at the text column side */
.hero-image-overlay-fade {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to right,
    var(--offwhite) 0%,
    rgba(245, 244, 242, 0.85) 18%,
    rgba(245, 244, 242, 0) 55%
  );
  pointer-events: none;
}
```

**CSS notes:**

- The `--offwhite` hex is `#F5F4F2` — that's what the `rgba(245, 244, 242, ...)` values correspond to. If `--offwhite` ever changes in `BRAND.md`, these rgba values need to be updated to match (or rewritten using `color-mix()` once browser support is universal).
- `pointer-events: none` on the overlays prevents them from intercepting clicks meant for any future content.
- `mix-blend-mode` is the key mechanism. It tells the browser "blend this layer with what's behind it using the given formula." `multiply` deepens shadows. `color` applies hue and saturation without affecting luminance.
- The multiply opacity of `0.55` and accent opacity of `0.15` are tuning values — Ade may want to adjust after seeing it in the live site. Flag these as reviewable.

---

### Responsive behaviour — mobile

At the mobile breakpoint (`max-width: 768px`), the hero stacks: text on top, image below (or hidden entirely — see decision point).

**Decision required from Ade:** On mobile, should the image appear at all?

Two options:

**A. Hide the image on mobile.** Simpler, faster, keeps the mobile hero clean and text-focused.

```css
@media (max-width: 768px) {
  .hero {
    grid-template-columns: 1fr;
  }
  .hero-image {
    display: none;
  }
}
```

**B. Show the image below the text, full-width, shorter height.** Adds atmospheric context on mobile too, at the cost of page weight.

```css
@media (max-width: 768px) {
  .hero {
    grid-template-columns: 1fr;
  }
  .hero-image {
    height: 220px;
  }
  .hero-image-overlay-fade {
    background: linear-gradient(
      to bottom,
      rgba(245, 244, 242, 0) 0%,
      rgba(245, 244, 242, 0) 70%,
      var(--offwhite) 100%
    );
  }
}
```

Recommended: **Option A for now.** Ship it, see how the mobile hero feels, revisit if needed. Default to Option A unless Ade has already specified otherwise.

---

### Animation

The hero H1 already has `transition:animate="fade"` or equivalent per Task 4. No changes needed there.

For the image itself: add a subtle fade-in on page load so it doesn't appear abruptly. Apply this to the `.hero-image` wrapper:

```css
.hero-image {
  /* ...existing rules... */
  animation: hero-image-fade-in 0.8s ease-out 0.15s both;
}

@keyframes hero-image-fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}
```

The `0.15s` delay lets the H1 start animating first, so the text leads and the image arrives just after.

---

### Accessibility

- `alt=""` and `aria-hidden="true"` are correct for decorative imagery. Do not add descriptive alt text — it would be redundant with the H1 and eyebrow.
- Contrast: the fade ensures the left-column text sits on `--offwhite`, so contrast ratios for the H1 (charcoal on offwhite) and body (`--body` on offwhite) are unchanged and already compliant.
- The `prefers-reduced-motion` query should disable the fade-in animation:

```css
@media (prefers-reduced-motion: reduce) {
  .hero-image {
    animation: none;
  }
}
```

Add this alongside any other `prefers-reduced-motion` rules in `global.css`.

---

### Verification

1. **Desktop:** The homepage hero shows the workshop photo on the right half, with a clean charcoal+accent duotone tone (warmer/cooler than plain greyscale — shadows should feel like they belong with the `--charcoal` palette). The photo fades smoothly into `--offwhite` behind the text column; no hard seam is visible at the fade boundary.
2. **Text column:** Eyebrow, H1, body copy, and the two CTAs render exactly as before. The accent word "expensive to get wrong." is still `--accent` blue. No text sits over the photo or over the fade — it should all be on clean `--offwhite`.
3. **Animation:** On first page load, the H1 slides up, and the hero image fades in about 0.15s after the H1 starts. The image does not flash or pop.
4. **Mobile (≤768px):** The image is hidden (Option A) — the hero is pure text on `--offwhite`, stacked as it was before this task.
5. **Reduced motion:** With `prefers-reduced-motion: reduce` set in the browser, the hero image appears instantly without fade-in.
6. **Build check:** `npm run build` completes without errors. The built site uses the optimised WebP variant with JPEG fallback. Image file appears in the built assets directory.
7. **No regressions:** Other pages (services, client-successes, about, insights, case studies) are visually unchanged. The nav CTA still scrolls to `#contact` on the homepage, still opens the Google Calendar URL elsewhere.
8. **No layout shift:** The image loads into a reserved 50%-width column — there should be zero CLS (cumulative layout shift) on the hero.

---

### Tuning notes (for Ade to review after implementation)

The following values are reasonable defaults but may want adjustment once seen in the live site at full resolution:

- `.hero-image-overlay-multiply` opacity: currently `0.55`. Lower (e.g. `0.40`) to let more photo detail through; higher (e.g. `0.70`) to push further toward a dark, moody feel.
- `.hero-image-overlay-accent` opacity: currently `0.15`. This is deliberately very subtle — it's the difference between "greyscale photo" and "tonally integrated photo." Higher values (e.g. `0.25`) will make the accent shift more obvious and potentially cooler/bluer.
- Fade gradient stops: currently `0% → 18% → 55%`. Shift the `55%` stop left (e.g. `45%`) for a harder fade, or right (e.g. `65%`) for a softer one.

These three values are the tuning surface. The rest of the treatment should not need to change.
