# Mattermind Website V1.0

Single-page marketing site for **Mattermind** — a deep-tech R&D lab embedding intelligence into the foundations of reality.

## Running locally

There is no build step.

```bash
open index.html
```

(or open the file in any modern browser). Tailwind CSS, Google Fonts, and all images are loaded directly by the page.

## Stack

- HTML + CSS + minimal vanilla JavaScript
- [Tailwind CSS](https://tailwindcss.com) (via CDN — no PostCSS / no build pipeline)
- [Google Fonts](https://fonts.google.com): Noto Serif Display (headings), Sora (body), Share Tech Mono (caption tags)
- HTML5 Canvas for the four particle-effect overlays (hero, bloom embers, divider drift, deep-tech spiral)
- IntersectionObserver for scroll-triggered reveals + canvas pause/resume

## File structure

```
.
├── index.html                ← single-file site (~2,600 lines)
├── design-system.md          ← user-supplied design system
├── project-brief.md          ← user-supplied brief
├── PROJECT_KNOWLEDGE.md      ← full hand-off doc — read first if continuing the build
├── Web v1.0.jpg              ← desktop flat design reference
├── Mobile v1.0.jpg           ← mobile flat design reference
└── images/
    ├── hero_bg_2400.webp     ← hero background
    ├── quantum_bloom_img.webp ← Section B bloom (warm/cool gradient bloom)
    ├── particle_divider.webp ← Section D horizon divider
    ├── deeptech_bloom.webp   ← Section F deep-tech bloom
    ├── footer_img_mono.webp  ← Section H industrial line-art
    ├── mm_logo.svg           ← navbar wordmark
    ├── mm_indent.png         ← hero centre M-mark (alpha PNG; not converted)
    ├── mm_indent_small_grey.svg ← divider M-mark
    └── panel1/2/3_img.svg    ← Section E card illustrations
```

## Testing notes

- Mobile (≤767px) and desktop (≥1024px) layouts are deliberately distinct — many sections have mobile-only spacing and structural overrides.
- Recommended browser breakpoints to spot-check: 1920, 1440, 1024, 768, 430, 375.
- All animation / motion respects `prefers-reduced-motion: reduce` — verify in Accessibility devtools.
- Performance: hero, bloom-pulse, divider, and deep-tech canvases each cap at 24fps and pause via IntersectionObserver when off-screen. Expected fps target is ~60 on a mid-tier laptop.
- Contact form (`#contactForm` in Section H) currently has `action="#"` — the `name`, `inquiry_type`, and `thoughts` fields are semantic and ready to wire to Formspree / Netlify Forms / a custom POST endpoint.

## Deployment

Designed for static hosting (GitHub Pages, Netlify, or any static CDN). All paths are relative — push the project root and point the host at it.

## Continuing the build

For full architectural and historical context (design system, section-by-section implementation, motion systems, perf learnings, gotchas), read **[PROJECT_KNOWLEDGE.md](PROJECT_KNOWLEDGE.md)** before making changes.
