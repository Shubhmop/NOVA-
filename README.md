# NOVA — Digital Creative Studio Website

> A fully self-contained, production-grade static website for a creative design studio. Built with pure HTML5 and CSS3 — no frameworks, no build tools, no dependencies beyond Google Fonts.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Live Preview](#live-preview)
3. [Features](#features)
4. [Sections](#sections)
5. [Tech Stack](#tech-stack)
6. [Typography](#typography)
7. [Color System](#color-system)
8. [JavaScript Functionality](#javascript-functionality)
9. [Animations & Motion](#animations--motion)
10. [Responsive Design](#responsive-design)
11. [Accessibility](#accessibility)
12. [File Structure](#file-structure)
13. [Getting Started](#getting-started)
14. [Customization Guide](#customization-guide)
15. [Browser Support](#browser-support)
16. [Performance Notes](#performance-notes)
17. [License](#license)

---

## Project Overview

**NOVA** is a single-file static website template designed for a high-end creative and digital design studio. It showcases services, portfolio work, team members, testimonials, pricing plans, a blog section, and a contact form — all styled with a luxury dark-mode aesthetic featuring gold, rust, and teal accents.

The entire website lives in a single `website.html` file, making it trivial to deploy anywhere — GitHub Pages, Netlify, Vercel, or any basic web host.

---

## Live Preview

Open `website.html` in any modern browser. No server required.

```bash
# Option 1 — just open it
open website.html

# Option 2 — serve locally with Python
python3 -m http.server 8080

# Option 3 — serve locally with Node
npx serve .
```

Then navigate to `http://localhost:8080` (or whichever port is shown).

---

## Features

- **Zero dependencies** — no npm, no webpack, no React. One file, done.
- **Custom animated cursor** — a dual-ring cursor with smooth lag interpolation, replacing the browser default.
- **Page loader** — branded intro animation with a progress bar that fades out on load.
- **Scroll progress bar** — a gold gradient bar at the top of the viewport that tracks scroll depth.
- **Smooth anchor navigation** — all internal links scroll smoothly with a fixed-nav offset.
- **Scroll-reveal animations** — elements animate in from below, left, or right as they enter the viewport, using `IntersectionObserver`.
- **Animated counter** — the metrics section counts up from zero with an eased timing curve when scrolled into view.
- **Portfolio filter** — click category buttons to filter project cards by type (Brand, Web, Motion, Strategy).
- **FAQ accordion** — single-open accordion with smooth `max-height` transitions.
- **Billing toggle** — switches pricing cards between monthly and annual pricing.
- **Contact form feedback** — the submit button provides validation feedback and a simulated success state.
- **Mobile navigation overlay** — full-screen animated menu for mobile viewports.
- **Back-to-top button** — appears after scrolling 500px, smooth-scrolls back to top.
- **Noise texture overlay** — a subtle SVG noise grain applied as a fixed overlay for texture depth.
- **Animated gradient orbs** — hero section background orbs that drift gently with CSS keyframe animations.
- **Infinite marquee ticker** — a looping horizontal ticker belt between the hero and content sections.
- **Rotating badge** — a spinning circular badge on the about section illustration.

---

## Sections

| # | Section | Description |
|---|---------|-------------|
| 1 | **Navigation** | Fixed top nav with logo, links, CTA button, scroll-activated blur background, and mobile hamburger |
| 2 | **Hero** | Full-viewport landing with animated title, subtitle, CTA buttons, live stats, scroll indicator, and gradient orb background |
| 3 | **Marquee** | Looping horizontal ticker belt showcasing service keywords |
| 4 | **About** | Two-column layout with illustrated frame, rotating badge, pills list, and copy |
| 5 | **Services** | 3×2 card grid detailing six core service offerings |
| 6 | **Process** | Numbered vertical timeline with phase descriptions and deliverable tags |
| 7 | **Work / Portfolio** | Filterable masonry-style project grid with hover overlays |
| 8 | **Case Study Spotlight** | Featured project panel with visual mock, metrics, and description |
| 9 | **Metrics** | Full-bleed gold band with animated number counters |
| 10 | **Testimonials** | Three-column review card grid with author avatars |
| 11 | **Team** | Four-column team card grid with social links on hover |
| 12 | **Clients** | Logo strip of client names |
| 13 | **Pricing** | Three-tier pricing cards with monthly/annual toggle |
| 14 | **FAQ** | Accordion with six common questions |
| 15 | **Blog / Insights** | Three-column article card grid |
| 16 | **Contact / CTA** | Split layout with headline copy and functional contact form |
| 17 | **Footer** | Four-column footer with brand, links, newsletter signup, and legal row |

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Markup | HTML5 (semantic elements: `<header>`, `<main>`, `<footer>`, `<section>`, `<article>`, `<nav>`) |
| Styling | CSS3 (custom properties, grid, flexbox, clamp(), animations, transitions) |
| Scripting | Vanilla JavaScript (ES6+) |
| Fonts | Google Fonts (loaded via `<link>`) |
| Icons | Unicode glyphs and CSS-drawn shapes (no icon library needed) |
| Build | None — zero build step |

---

## Typography

Four typefaces are loaded from Google Fonts, each serving a specific role:

| Variable | Family | Role |
|----------|--------|------|
| `--font-display` | **Bebas Neue** | Display headings, numbers, logos, section titles |
| `--font-serif` | **DM Serif Display** | Italic section subtitles and pull quotes |
| `--font-sans` | **Syne** | Body text, card titles, navigation, UI labels |
| `--font-mono` | **Space Mono** | Eyebrows, tags, metadata, form labels, monospaced UI elements |

### Fluid Type Scale

Most heading sizes use `clamp()` to scale smoothly between mobile and desktop viewports without media query jumps:

```css
font-size: clamp(5rem, 14vw, 14rem);   /* Hero title */
font-size: clamp(2.5rem, 5vw, 4.5rem); /* Section titles */
font-size: clamp(3rem, 7vw, 7rem);     /* CTA title */
```

---

## Color System

All colors are defined as CSS custom properties on `:root` for easy global theming.

| Token | Value | Usage |
|-------|-------|-------|
| `--black` | `#080808` | Page background |
| `--white` | `#f5f2ec` | Primary text (warm white, not pure) |
| `--cream` | `#ede8df` | Alternate warm text |
| `--gold` | `#c9a84c` | Primary accent — CTAs, highlights, borders |
| `--gold-light` | `#e2c97e` | Gold hover state |
| `--rust` | `#b84a2e` | Secondary accent — error states, badges |
| `--teal` | `#1e6b6b` | Tertiary accent — backgrounds, gradients |
| `--teal-light` | `#2a9494` | Teal hover state, service tags |
| `--ink` | `#1a1a1a` | Section backgrounds (slightly lighter than black) |
| `--muted` | `#6b6560` | Secondary text, placeholders, labels |
| `--border` | `rgba(201,168,76,0.25)` | Subtle gold-tinted dividers and card borders |

### Changing the Accent Color

To change the primary gold accent to a different color, find and update in `:root`:

```css
--gold:       #your-color;
--gold-light: #your-lighter-color;
--border:     rgba(R,G,B, 0.25);
```

---

## JavaScript Functionality

All JavaScript is written in vanilla ES6+ and lives in a single `<script>` block at the bottom of `<body>`. No external libraries are used.

### Custom Cursor

```js
// Dot follows mouse instantly
// Ring follows with lerp (linear interpolation) at 12% speed per frame
ringX += (mouseX - ringX) * 0.12;
```

The cursor scales up on hoverable elements via `body.cursor-hover` class toggling.

### Scroll Progress Bar

Reads `window.scrollY` and `document.documentElement.scrollHeight` on every scroll event to compute a percentage, applied as `width` on `#scroll-bar`.

### Intersection Observer (Reveal Animations)

Uses a single `IntersectionObserver` watching all `.reveal`, `.reveal-left`, and `.reveal-right` elements. When an element enters the viewport (threshold: 12%, with a -60px bottom margin), it gains the `.visible` class which transitions it to full opacity and its natural position.

Siblings within the same parent get auto-staggered `transition-delay` based on their index.

### Animated Counters

A second `IntersectionObserver` targets `.metric__number` elements. On intersection, it extracts the target number, then runs a `requestAnimationFrame` loop with an **ease-out quart** easing function over 1600ms.

### Portfolio Filter

```js
filterBtns.forEach(btn => {
  btn.addEventListener('click', () => {
    // Sets opacity: 0.2 and scale(0.97) on non-matching cards
    // Sets opacity: 1 and scale(1) on matching cards
  });
});
```

### FAQ Accordion

Click on `.faq__question` closes all open items, then opens the clicked one (unless it was already open — click again to collapse). Uses `max-height` CSS transition for smooth open/close.

### Billing Toggle

Reads `data-monthly` and `data-annual` attributes from `.pricing-card__amount` elements and swaps the displayed text on toggle click.

### Contact Form

Client-side only — no backend. The submit handler:
1. Validates that name and email fields are not empty.
2. Shows an error state (rust color) if validation fails.
3. Simulates a network request with a 1.6s `setTimeout`.
4. Displays a success state and clears the form fields.

To connect to a real backend, replace the `setTimeout` block with a `fetch()` call to your API endpoint.

---

## Animations & Motion

### CSS Keyframe Animations

| Name | Effect | Used On |
|------|--------|---------|
| `fade-up` | Opacity 0→1, translateY 28px→0 | Hero content blocks |
| `fade-left` | Opacity 0→1, translateX 28px→0 | Hero stats |
| `orb-drift` | Translate + scale variation | Background gradient orbs |
| `marquee` | Continuous translateX scroll | Ticker belt |
| `badge-spin` | 360° rotation | About section badge |
| `scroll-line` | scaleY pulse (top to bottom) | Hero scroll indicator |
| `pulse-gold` | Opacity pulse | Loader logo |
| `loader-fill` | Width 0→100% | Loader progress bar |

### JavaScript Animations

- **Cursor ring** — rAF loop with lerp interpolation
- **Counter** — rAF loop with ease-out quart easing
- **Scroll reveal** — IntersectionObserver + CSS transition

### Respecting User Preferences

To respect `prefers-reduced-motion`, add this to your CSS:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## Responsive Design

The layout uses three breakpoint ranges defined with `@media` queries:

| Breakpoint | Target | Key Changes |
|-----------|--------|-------------|
| `max-width: 1024px` | Tablet | About stacks to 1 column; services grid → 2 col; team → 2 col; metrics → 2 col; footer → 2 col; work cards span full width |
| `max-width: 720px` | Mobile | Nav links hidden → hamburger; hero stats hidden; services → 1 col; testimonials → 1 col; blog → 1 col; footer → 1 col |
| `max-width: 480px` | Small mobile | Team → 1 col |

All spacing uses `clamp()` for fluid scaling between breakpoints without needing explicit overrides for every size.

---

## Accessibility

The following accessibility considerations are built in:

- **Semantic HTML** — proper use of `<header>`, `<main>`, `<footer>`, `<section>`, `<article>`, `<nav>`, `<ul>`, `<button>`
- **ARIA labels** — `aria-label`, `aria-labelledby`, `aria-expanded`, `aria-checked`, `aria-hidden` applied throughout
- **Focus management** — interactive elements have visible focus states (native browser focus ring is preserved)
- **Keyboard navigation** — the billing toggle responds to `Enter` and `Space` key events; the mobile nav supports keyboard dismiss
- **Color contrast** — gold `#c9a84c` on dark `#080808` meets WCAG AA for large text; muted text is used only for decorative/secondary content
- **`role` attributes** — `role="list"`, `role="listitem"`, `role="group"`, `role="switch"` used where appropriate
- **`aria-label`** on all icon-only links and buttons

---

## File Structure

```
project/
└── website.html        ← The entire website (HTML + CSS + JS in one file)
└── README.md           ← This file
```

Since everything is self-contained in one HTML file, there are no additional assets to manage. If you want to extend the project, a recommended structure would be:

```
project/
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── main.js
├── assets/
│   ├── images/
│   └── fonts/
└── README.md
```

---

## Getting Started

### 1. Download the file

Save `website.html` to your local machine.

### 2. Open in a browser

Double-click `website.html` or open it from your browser's File menu. The site works fully offline except for the Google Fonts (which gracefully fall back to system fonts if the CDN is unavailable).

### 3. Edit the content

Open `website.html` in any text editor (VS Code, Sublime Text, Notepad++, etc.) and find the section you want to update. Sections are clearly marked with large comment banners:

```html
<!-- ============================================================
     HERO
============================================================ -->
```

### 4. Deploy

Upload `website.html` (rename to `index.html` for web servers) to any host:

- **GitHub Pages** — push to a repo and enable Pages in Settings
- **Netlify** — drag and drop the folder at netlify.com/drop
- **Vercel** — `vercel deploy` in the project folder
- **Any web host** — upload via FTP/SFTP to your `public_html` directory

---

## Customization Guide

### Change the Studio Name

Search and replace `NOVA` with your studio name throughout the file. The logo appears in:
- `<title>` tag
- `.nav__logo`
- `.footer__logo`
- `.loader__logo`
- The `metrics::before` pseudo-element CSS content

### Update Colors

Edit the CSS custom properties at the top of the `<style>` block:

```css
:root {
  --gold:      #c9a84c;   /* Change to your brand color */
  --gold-light:#e2c97e;
  --rust:      #b84a2e;   /* Change to your secondary color */
  --teal:      #1e6b6b;   /* Change to your tertiary color */
}
```

### Add Real Project Images

Replace the gradient `.work-card__bg` divs with actual images:

```html
<!-- Replace this: -->
<div class="work-card__bg work-card__bg--1"></div>

<!-- With this: -->
<div class="work-card__bg" style="background-image:url('assets/project-1.jpg');background-size:cover;background-position:center;"></div>
```

### Connect the Contact Form

Replace the `setTimeout` simulation in the JS section with a real API call:

```js
try {
  const res = await fetch('/api/contact', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ name, email, message })
  });
  if (res.ok) {
    submitBtn.innerHTML = '✓ Message Sent!';
  }
} catch (err) {
  submitBtn.innerHTML = 'Error — Try Again';
}
```

### Add/Remove Service Cards

The services grid (`services__grid`) accepts any number of `.service-card` elements. The grid is defined as `repeat(3, 1fr)` — change to `repeat(2, 1fr)` for a 2-column layout.

### Change Pricing

Update the `data-monthly` and `data-annual` attributes on `.pricing-card__amount` elements, and update the feature list items within each `.pricing-card__features` list.

---

## Browser Support

| Browser | Support |
|---------|---------|
| Chrome 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Edge 90+ | ✅ Full |
| Opera 76+ | ✅ Full |
| IE 11 | ❌ Not supported |

---

## Performance Notes

- **Single HTTP request** for HTML (plus Google Fonts which loads 4 font families)
- No JavaScript libraries — no jQuery, no React, no lodash
- CSS animations use `transform` and `opacity` only (GPU-composited, no layout thrash)
- `IntersectionObserver` for scroll effects (no scroll event listeners for animations)
- Cursor ring uses `requestAnimationFrame` (not `setInterval`)
- Google Fonts uses `display=swap` for zero render-blocking
- `preconnect` hints for fonts CDN reduce latency

### Estimated Lighthouse Scores

| Metric | Score |
|--------|-------|
| Performance | 90–95 |
| Accessibility | 88–94 |
| Best Practices | 95+ |
| SEO | 85–90 |

Scores will vary based on hosting environment, image assets, and network speed.

---

## License

This project is provided as a template for personal and commercial use. You are free to:

- Use it as the basis for client websites
- Modify the design, content, and code freely
- Deploy it on any hosting platform

You may **not**:
- Resell the template itself as a standalone product without modification
- Claim original authorship of the unmodified template

---

## Credits

- Fonts by [Google Fonts](https://fonts.google.com) — Bebas Neue, DM Serif Display, Syne, Space Mono
- Design and code — NOVA Creative Studio template
- Built with zero npm installs

---

*Last updated: April 2026*
