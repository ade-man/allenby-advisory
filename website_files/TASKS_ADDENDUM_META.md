# TASKS_ADDENDUM_META.md — Open Graph Meta Tags and Favicon

This task can be completed at any point after Task 2 (Base layout and shared components).

---

## Task 11 — Open Graph meta tags and favicon

**Goal:** Add favicon support and Open Graph / Twitter Card meta tags to every page.

---

### Part A — Favicon files

**Files to add to `public/`:**

Copy all of the following into the Astro `public/` directory (they will be served from the site root):

| File | Size | Purpose |
|---|---|---|
| `favicon.ico` | 16+32px | Legacy browser tab icon |
| `favicon-16x16.png` | 16×16 | Modern browser tab icon |
| `favicon-32x32.png` | 32×32 | Modern browser tab icon (2×) |
| `apple-touch-icon.png` | 180×180 | iOS home screen |
| `favicon-192x192.png` | 192×192 | Android / PWA |
| `favicon-512x512.png` | 512×512 | PWA splash screen |
| `site.webmanifest` | — | PWA manifest |

All files are provided alongside this document.

---

### Part B — Update `Base.astro` `<head>`

Add the following lines inside `<head>` in `src/layouts/Base.astro`, after the Google Fonts link:

```html
<!-- Favicon -->
<link rel="icon" href="/favicon.ico" sizes="any">
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
<link rel="apple-touch-icon" href="/apple-touch-icon.png">
<link rel="manifest" href="/site.webmanifest">
<meta name="theme-color" content="#1A1A1A">
```

---

### Part C — Add OG and Twitter meta props to `Base.astro`

Update the `Base.astro` props interface to accept optional OG fields:

```astro
---
import { ViewTransitions } from 'astro:transitions';

interface Props {
  title: string;
  description: string;
  ogTitle?: string;
  ogDescription?: string;
  ogImage?: string;
  ogType?: string;
}

const {
  title,
  description,
  ogTitle = title,
  ogDescription = description,
  ogImage = 'https://www.allenby-advisory.com/og-default.png',
  ogType = 'website',
} = Astro.props;

const canonicalURL = new URL(Astro.url.pathname, Astro.site);
---
```

Add these meta tags inside `<head>`:

```html
<!-- Canonical -->
<link rel="canonical" href={canonicalURL}>

<!-- Open Graph -->
<meta property="og:title" content={ogTitle}>
<meta property="og:description" content={ogDescription}>
<meta property="og:url" content={canonicalURL}>
<meta property="og:type" content={ogType}>
<meta property="og:image" content={ogImage}>
<meta property="og:site_name" content="Allenby Advisory">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content={ogTitle}>
<meta name="twitter:description" content={ogDescription}>
<meta name="twitter:image" content={ogImage}>
```

---

### Part D — OG image

Create a default OG image (`og-default.png`) at 1200×630px.

**Design spec:**
- Background: #1A1A1A (charcoal)
- "Allenby Advisory" in Julius Sans One, white, centred, ~48px
- "Event technology and digital" below in Archivo 400, #888780, ~18px, tracked, uppercase
- No logo graphic — text only (matches the brand's typographic identity)

Place in `public/og-default.png`.

This single image is used for all pages. Per-page OG images are not required at launch — the brand name image works well for link previews across all contexts.

---

### Part E — Per-page meta content

Pass `title` and `description` from each page to `Base.astro`. These values double as the OG title and description.

| Page | title | description |
|---|---|---|
| Homepage | Allenby Advisory — Event Technology and Digital Consultancy | Allenby Advisory helps event leaders choose, implement and get results from the right technology — without the learning curve, the wasted budget, or the failed launches. |
| Services | Services — Allenby Advisory | Event technology consultancy across advisory, project delivery and capability building. Choose the level of support that fits where you are right now. |
| Client Successes | Client Successes — Allenby Advisory | Case studies from event technology projects across navigation, meetings programmes, lead capture and global research. |
| About | About — Allenby Advisory | 10+ years of specialist event technology and digital experience. One point of contact, a whole team behind it. |
| Insights | Insights — Allenby Advisory | Practical thinking on event technology, digital strategy and audience engagement — drawn from projects, research and conversations across the industry. |
| Incosmetics Global | Incosmetics Global: Lead Capture Strategy — Allenby Advisory | How a new NFC-based content capture technology multiplied leads and created a new exhibitor revenue stream at Incosmetics Global. |
| RX Global Research | RX Global: Attendee Behavioural Archetypes — Allenby Advisory | How a global research programme produced an award-winning framework for understanding attendee needs across 68 events in 10 countries. |

---

### Verification

- Favicon appears in browser tab on all pages
- Apple touch icon works (test in Safari responsive mode or on device)
- Run each page URL through [opengraph.xyz](https://opengraph.xyz) or Facebook's Sharing Debugger — title, description and image should all render correctly
- `site.webmanifest` loads without 404 (check Network tab)
- Canonical URLs are correct and absolute (not relative)
- No console errors
