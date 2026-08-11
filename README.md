# Nehal Aftab — Portfolio

A single-file personal portfolio for **Nehal Aftab** — Frontend Developer, UI/UX Designer, and Canva Campus Ambassador at FAST-NUCES Chiniot-Faisalabad. Built as a "contact sheet": every project is presented like a numbered frame on a photographer's proof sheet, rather than another templated card grid.

**Live site:** 

---

## Table of Contents

- [Concept](#concept)
- [Features](#features)
- [Design System](#design-system)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Deployment](#deployment)
- [Customization](#customization)
- [Accessibility & Performance](#accessibility--performance)
- [Browser Support](#browser-support)
- [Credits](#credits)
- [Contact](#contact)
- [License](#license)

---

## Concept

Most developer portfolios default to the same shapes: a bento grid of stats, a terminal window, a glowing gradient name. This one leans into something more personal — Nehal does photography and runs visual identity for two campus organizations, so the site borrows from a photographer's **contact sheet**: work is catalogued as numbered frames (`F01`, `F02`…), key panels carry crop-mark corner brackets like registration marks, and the palette is warm paper and ink rather than the usual near-black-plus-neon developer aesthetic.

The type system reinforces it — **Fraunces** (an expressive serif) for headlines, **Manrope** for body copy, and **Space Mono** for labels and frame numbers, standing in for the Inter + JetBrains Mono pairing almost every AI-generated dev portfolio reaches for by default.

## Features

- **Contact-sheet project grid** — each project is a numbered frame; flagship projects span two columns
- **Crop-mark motif** — corner brackets on the hero and about panels, animated in on scroll
- **Custom cursor** — a dot + trailing ring that expands on hover, auto-disabled on touch devices and for `prefers-reduced-motion`
- **Magnetic tilt** — subtle perspective tilt on cards, tracking the pointer
- **Film-grain overlay** — a faint SVG noise texture for tactile depth
- **Marquee ticker** — a slow-scrolling strip of roles and affiliations
- **Staggered hero entrance** and scroll-triggered reveals (skipped entirely under reduced motion)
- **Fully responsive** — collapses gracefully from a 3-column contact sheet down to a single column
- **Zero dependencies** — no framework, no bundler, no npm install

## Design System

**Color**

| Token | Value | Used for |
|---|---|---|
| `--paper` | `#F2EEE4` | Base background |
| `--paper-deep` | `#E7E0CC` | Panels, hover states |
| `--ink` | `#1A1712` | Primary text |
| `--ink-soft` | `#635C4C` | Secondary text |
| `--ink-faint` | `#948C77` | Labels, meta, frame numbers |
| `--cobalt` | `#2C3BC7` | Primary accent — links, CTAs |
| `--ochre` | `#B9822A` | Secondary accent — the "Current" tag |

**Type**

| Role | Typeface | Where |
|---|---|---|
| Display | Fraunces | Name, section headings, pull-quotes |
| Body | Manrope | Paragraphs, UI copy |
| Mono | Space Mono | Eyebrows, frame numbers, tags, nav wordmark |

All tokens live as CSS custom properties in `:root`, so the whole palette and type scale can be changed from one place.

## Tech Stack

- **HTML5** — semantic sectioning
- **CSS3** — custom properties, Grid, Flexbox, `prefers-reduced-motion` support
- **Vanilla JavaScript** — `IntersectionObserver` for scroll reveals, `requestAnimationFrame` for the cursor and entrance animation
- **Google Fonts** — Fraunces, Manrope, Space Mono
- No React, no build tooling, no package.json

## Project Structure

```
nehal-aftab-portfolio/
└── index.html    # markup, styles, and scripts — all in one file
```

Everything ships in a single HTML file by design: no build step means it can be opened, edited, and redeployed by anyone without setting up tooling.

## Getting Started

```bash
git clone https://github.com/nehalaftab05-web/<repo-name>.git
cd <repo-name>
```

Then just open `index.html` in a browser — double-click it, or run a quick local server if you'd rather avoid `file://` quirks:

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

No `npm install`, no build command. It's a static file.

## Deployment

**GitHub Pages** (matches how the rest of Nehal's projects are hosted):

1. Rename the file to `index.html` if it isn't already, and push the repo to GitHub
2. Go to **Settings → Pages**
3. Set **Source** to the `main` branch, root folder
4. The site goes live at `https://nehalaftab05-web.github.io/<repo-name>/`

**Vercel / Netlify** also work with a plain drag-and-drop or Git import — no framework preset needed, just a static site.

## Customization

Since there's no CMS or data file, content lives directly in the markup:

| To change… | Edit… |
|---|---|
| Colors, fonts, spacing | `:root` custom properties at the top of `<style>` |
| Hero headline & bio | `<section class="hero">` |
| Projects | `<section id="work">` — each `<article class="frame">` is one project; add the `featured` class to span two columns |
| Skills | `<section id="skills">` — one `.skill-row` per category |
| Experience | `<section id="experience">` — `.ledger` for primary roles, `.ledger-compact` for shorter campus involvement |
| Contact links | `<section id="contact">` |

## Accessibility & Performance

- Respects `prefers-reduced-motion`: disables the custom cursor, tilt, ticker animation, and scroll reveals for anyone who has it set
- Custom cursor and tilt only activate on devices with `hover: hover` and `pointer: fine` — skipped entirely on touch
- Visible `:focus-visible` states on every interactive element
- Semantic `<section>` / `<article>` structure with descriptive headings throughout
- No external JS dependencies to load — only two font requests

## Browser Support

Built for modern evergreen browsers (Chrome, Firefox, Safari, Edge) using CSS Grid, custom properties, and `IntersectionObserver`. Not tested against or intended for Internet Explorer.

## Credits

Typefaces via [Google Fonts](https://fonts.google.com): [Fraunces](https://fonts.google.com/specimen/Fraunces), [Manrope](https://fonts.google.com/specimen/Manrope), [Space Mono](https://fonts.google.com/specimen/Space+Mono).

## Contact

- **Email** — [nehalaftabwork@gmail.com](mailto:nehalaftabwork@gmail.com)
- **GitHub** — [github.com/nehalaftab05-web](https://github.com/nehalaftab05-web)
- **LinkedIn** — [linkedin.com/in/nehal-aftab](https://linkedin.com/in/nehal-aftab)

## License

The code structure in this repo is free to reference or fork for your own portfolio. The written content, project descriptions, and personal branding belong to Nehal Aftab — please don't republish those as your own.
