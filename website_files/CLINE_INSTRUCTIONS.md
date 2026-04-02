# Cline Instructions — Allenby Advisory Website

## Project overview

You are building the Allenby Advisory website using Astro. This is a 5-page professional consultancy site for an event technology advisory practice. All design decisions, copy, and brand rules are defined in the reference files in this folder. Do not deviate from them.

## How to use these files

Read these files before starting any task:

| File | Purpose |
|---|---|
| `BRAND.md` | Colours, fonts, spacing, component rules — the single source of truth for all visual decisions |
| `CONTENT_HOME.md` | All copy for the homepage |
| `CONTENT_SERVICES.md` | All copy for the Services page |
| `CONTENT_CLIENT_SUCCESSES.md` | All copy for the Client Successes page |
| `CONTENT_ABOUT.md` | All copy for the About page |
| `CONTENT_INSIGHTS.md` | All copy for the Insights page |
| `TASKS.md` | Sequential build tasks — complete one at a time |

## Critical rules

1. **Always read BRAND.md before writing any CSS or component code.** Every colour, font, spacing value and component pattern is defined there. Do not guess or improvise.
2. **Copy is final.** Use the exact text from the CONTENT_*.md files. Do not paraphrase, summarise or rewrite.
3. **Complete one task at a time.** Each task in TASKS.md is scoped to avoid token limits. Finish a task fully before moving to the next.
4. **No inline styles.** Use Astro component props and the global CSS custom properties defined in BRAND.md.
5. **Test after each task.** Run `npm run dev` and confirm the page renders without errors before marking a task complete.
6. **Ask before adding dependencies.** The only approved packages are listed in TASKS.md Task 1. Do not install others without confirmation.

## Stack

- **Framework:** Astro 4.x
- **Styling:** Global CSS with custom properties (no Tailwind, no CSS modules)
- **Animation:** Astro View Transitions + CSS animation (no GSAP unless explicitly added in a later task)
- **Fonts:** Google Fonts — loaded via `<link>` in the base layout
- **Deployment target:** Static (output: 'static')

## Folder structure to create

```
allenby-advisory/
├── public/
│   └── fonts/          (empty — fonts loaded from Google)
│   └── images/         (placeholder — images added later)
├── src/
│   ├── components/
│   │   ├── Nav.astro
│   │   ├── Footer.astro
│   │   ├── Hero.astro
│   │   ├── SectionLabel.astro
│   │   ├── ServiceTile.astro
│   │   ├── CaseCard.astro
│   │   ├── Testimonial.astro
│   │   ├── InsightItem.astro
│   │   ├── MetricBox.astro
│   │   └── Button.astro
│   ├── layouts/
│   │   └── Base.astro
│   ├── pages/
│   │   ├── index.astro
│   │   ├── services.astro
│   │   ├── client-successes.astro
│   │   ├── about.astro
│   │   └── insights.astro
│   └── styles/
│       └── global.css
├── astro.config.mjs
└── package.json
```
