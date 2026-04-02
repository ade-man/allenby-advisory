# BRAND.md — Allenby Advisory Design System

This is the single source of truth for all visual decisions. Read this before writing any CSS, component or layout code.

---

## 1. Colour palette

Define these as CSS custom properties in `src/styles/global.css`.

```css
:root {
  --charcoal:   #1A1A1A;   /* Primary dark — backgrounds, headings, buttons */
  --offwhite:   #F5F4F2;   /* Page background */
  --white:      #FFFFFF;   /* Content surface (cards, content columns) */
  --body:       #2e2d2b;   /* All body text — NOT mid-grey */
  --midgrey:    #888780;   /* Captions, labels, metadata, eyebrows only */
  --lightgrey:  #D3D1C7;   /* Borders and dividers — 0.5px */
  --accent:     #2C5F8A;   /* Links, result badges, blockquote borders — max once per section */
}
```

### Usage rules
- **Page / section backgrounds:** `--offwhite`
- **Content surfaces (tiles, cards):** `--white`
- **Body text:** `--body` (#2e2d2b) — never use `--midgrey` for readable body copy
- **Captions, metadata, eyebrow labels:** `--midgrey` only
- **Borders and rules:** `--lightgrey` at `0.5px solid`
- **Accent:** `--accent` used at most once per section — links, result badges, blockquote left-border
- **Dark sections** (network strip, footer CTA): `--charcoal` background, white headings, `#c8c6c2` body text

---

## 2. Typography

### Font loading
Add this `<link>` in `Base.astro` inside `<head>`:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Archivo+Condensed:wght@700&family=Archivo:wght@400;700&family=Julius+Sans+One&display=swap" rel="stylesheet">
```

### Font roles

| Role | Font | Weight | Case | Where used |
|---|---|---|---|---|
| Brand name | Julius Sans One | 400 | Title case | Nav logo, footer brand name only |
| Page H1 | Archivo Condensed | 700 | Title case | Page titles |
| Section H2 | Archivo Condensed | 700 | Title case | Section headings |
| Card / tile H3 | Archivo Condensed | 700 | Title case | Card and tile headings |
| Navigation links | Archivo | 400 | ALL CAPS, tracked | Nav items |
| Section eyebrows | Archivo | 400 | ALL CAPS, tracked | Short labels above H2 |
| Content type tags | Archivo | 700 | ALL CAPS, tracked | "Article", "Podcast", "Panel" |
| CTA buttons | Archivo | 400 | ALL CAPS, tracked | All buttons |
| Body text | Archivo | 400 | Sentence case | All readable paragraphs |
| Metadata / captions | Archivo | 400 | ALL CAPS, tracked | Event tags, publisher, cite |

### Critical rule
**Two weights only: 400 and 700.** Never use 500 or 600.

### CSS classes

```css
/* In global.css */

.font-brand {
  font-family: 'Julius Sans One', sans-serif;
  font-weight: 400;
}

.font-display {
  font-family: 'Archivo Condensed', sans-serif;
  font-weight: 700;
  letter-spacing: 0.01em;
}

.font-label {
  font-family: 'Archivo', sans-serif;
  font-size: 11px;
  letter-spacing: 0.10em;
  text-transform: uppercase;
  color: var(--midgrey);
}

.font-body {
  font-family: 'Archivo', sans-serif;
  font-weight: 400;
  font-size: 15px;
  line-height: 1.7;
  color: var(--body);
}
```

---

## 3. Spacing

```css
:root {
  --space-xs:  8px;
  --space-sm:  16px;
  --space-md:  24px;
  --space-lg:  40px;
  --space-xl:  56px;
  --space-2xl: 72px;
}
```

- **Section padding:** `var(--space-2xl) var(--space-lg)` (72px top/bottom, 40px left/right)
- **Card padding:** `28px`
- **Between sections:** `border-bottom: 0.5px solid var(--lightgrey)`
- **Grid gaps:** `0.5px` (creates hairline separators when background is `--lightgrey`)

---

## 4. Borders and surfaces

```css
/* Standard border */
border: 0.5px solid var(--lightgrey);

/* Accent left border (used on audience box, testimonial blockquotes) */
border-left: 3px solid var(--accent);

/* Grid separator technique — set gap to 0.5px, parent background to --lightgrey */
.grid-separator {
  display: grid;
  gap: 0.5px;
  background: var(--lightgrey);
  border: 0.5px solid var(--lightgrey);
}
.grid-separator > * {
  background: var(--white);
}
```

No border-radius on any element. All corners are square (consistent with the brand's confident, architectural feel).

---

## 5. Navigation component

```
Nav.astro props: none (self-contained)

Structure:
  nav (border-bottom: 0.5px solid --lightgrey, bg: --offwhite)
    .nav-logo  →  Julius Sans One, 15px, --charcoal
    ul.nav-links  →  flex, gap 28px
      li > a  →  Archivo 11px, tracked, uppercase, --midgrey
        [active state]  →  color: --charcoal, border-bottom: 0.5px solid --charcoal
    a.nav-cta  →  Archivo 11px, tracked, uppercase, bg: --charcoal, color: --white, padding 10px 20px
```

Active page detection: use `Astro.url.pathname` to set active class.

---

## 6. Button component

```
Button.astro props:
  - label: string (required)
  - href: string (required)
  - variant: 'primary' | 'ghost' | 'light' (default: 'primary')

primary:  bg --charcoal, color --white, padding 13px 28px
ghost:    no bg, color --midgrey, border-bottom 0.5px solid --lightgrey
light:    bg --white, color --charcoal (for use on dark sections)

All buttons: Archivo 11px, letter-spacing 0.09em, text-transform uppercase, no border-radius
```

---

## 7. Section label (eyebrow) component

```
SectionLabel.astro props:
  - text: string

Output: <p class="section-label">{text}</p>

CSS:
  font-family: Archivo
  font-size: 11px
  letter-spacing: 0.12em
  text-transform: uppercase
  color: var(--midgrey)
  margin-bottom: 28px
```

---

## 8. Service tile component

```
ServiceTile.astro props:
  - number: string  (e.g. "01")
  - category: string  (e.g. "Advisory")
  - title: string
  - body: string
  - href: string

Structure:
  div.service-tile (bg --white, padding 32px 28px)
    p.tile-num  →  "01 — Advisory"  →  11px, tracked, uppercase, --midgrey
    h3  →  Archivo Condensed 700, 20px, title case, --charcoal
    p  →  body text
    a  →  11px, tracked, uppercase, --accent, text-decoration none
```

---

## 9. Case card component

```
CaseCard.astro props:
  - result: string  (the badge text)
  - title: string
  - eventTag: string
  - body: string
  - href: string

Structure:
  div.case-card (bg --white, border 0.5px solid --lightgrey, padding 28px)
    p.result-badge  →  11px, tracked, uppercase, color --accent, border 0.5px solid --accent, padding 4px 10px, inline-block
    h3  →  Archivo Condensed 700, 22px, title case
    p.event-tag  →  11px, tracked, uppercase, --midgrey
    p  →  body text
    a  →  11px, tracked, uppercase, --accent
```

---

## 10. Testimonial component

```
Testimonial.astro props:
  - quote: string
  - name: string
  - role: string

Structure:
  div.testimonial (bg --white, border 0.5px solid --lightgrey, padding 28px)
    blockquote  →  Archivo 15px, italic, --charcoal, border-left 2px solid --accent, padding-left 16px
    cite  →  11px, tracked, uppercase, --midgrey, font-style normal
```

---

## 11. Metric box component

```
MetricBox.astro props:
  - number: string  (e.g. "100%")
  - description: string

Structure:
  div.metric-box (bg --charcoal, padding 16px)
    span.metric-num  →  Archivo Condensed 700, 36px, --white, display block
    p.metric-desc  →  11px, tracked, uppercase, #888780
```

---

## 12. Dark section pattern

Used for the network strip (homepage) and all footer CTAs:

```css
.dark-section {
  background: var(--charcoal);
  color: var(--white);
  padding: var(--space-2xl) var(--space-lg);
}

.dark-section h2 {
  font-family: 'Archivo Condensed', sans-serif;
  font-weight: 700;
  font-size: 34px;
  color: var(--white);
  letter-spacing: 0.01em;
  line-height: 1.06;
  margin-bottom: 16px;
}

.dark-section p {
  color: #c8c6c2;
  font-size: 15px;
  line-height: 1.65;
  max-width: 560px;
}

.dark-section .section-label {
  color: #555;
}
```

---

## 13. Footer component

```
Footer.astro props: none

Structure:
  footer (border-top 0.5px solid --lightgrey, bg --offwhite, padding 22px 40px)
    flex row, space-between
    .footer-brand  →  Julius Sans One, 13px, --charcoal  →  "Allenby Advisory"
    p  →  11px, tracked, uppercase, --midgrey  →  "Event technology and digital · © 2025"
```

---

## 14. Animation guidelines (Astro View Transitions)

Enable View Transitions in `Base.astro`:

```astro
---
import { ViewTransitions } from 'astro:transitions';
---
<head>
  <ViewTransitions />
</head>
```

### Per-element animations

Use `transition:animate` on elements that should animate on page entry:

```astro
<!-- Fade in -->
<h1 transition:animate="fade">...</h1>

<!-- Slide up (custom) — define in global.css -->
<div transition:animate="slide">...</div>
```

### Custom slide-up animation

```css
/* In global.css */
@keyframes slideUp {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}

.animate-slide-up {
  animation: slideUp 0.5s ease forwards;
}

/* Stagger children */
.animate-slide-up:nth-child(1) { animation-delay: 0s; }
.animate-slide-up:nth-child(2) { animation-delay: 0.1s; }
.animate-slide-up:nth-child(3) { animation-delay: 0.2s; }
```

Apply `transition:animate` to: hero H1, section headings, card grids (staggered), the dark network strip.

### Scroll-triggered reveals

Use the Intersection Observer API in a `<script>` tag within components that should reveal on scroll:

```js
// Add to any component that needs scroll reveal
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('is-visible');
      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.15 });

document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
```

```css
.reveal {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.5s ease, transform 0.5s ease;
}
.reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}
```

Add class `reveal` to: service tiles, case cards, testimonials, insight items, capability grid items.

---

## 15. Responsive breakpoints

```css
/* Mobile first */
:root {
  --bp-md: 768px;
  --bp-lg: 1024px;
}

/* Tablet */
@media (max-width: 768px) {
  /* Single column grids */
  /* Stack two-column layouts */
  /* Reduce hero font size to 36px */
  /* Nav collapses to hamburger — see Task 8 */
}

/* Desktop — primary design target */
/* All mockups are designed at ~1280px */
```

---

## 16. Skill pills (network section)

```css
.skill-pill {
  border: 0.5px solid #444;
  padding: 6px 14px;
  font-family: 'Archivo', sans-serif;
  font-size: 11px;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #aaa;
  display: inline-block;
}
```
