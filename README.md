# Luere website

Marketing microsite for **Luere** — the free, private macOS image compressor
("Smaller files. Same good looks."). It's the direct-download funnel and a
cross-promo hub for the maker's other projects (Puuunch, Luere Icon Studio).

Static **HTML + Tailwind CSS v4**. No framework, no build server — one page, one
stylesheet, a sprinkle of vanilla JS. Deployable to any static host.

## Stack

- **HTML** — a single `index.html`.
- **Tailwind CSS v4** — compiled from `src/input.css` to `dist/styles.css` via
  the Tailwind CLI. Design tokens (brand teal, font, animations) live in the
  `@theme` / base layers of `src/input.css`.
- **Font** — Instrument Sans (Google Fonts; see SEO.md to self-host later).
- **Vanilla JS** (inline in `index.html`) — download modal, scroll-reveal, footer
  year. No dependencies at runtime.

## Structure

```
luere-website/
├── index.html          # the whole page
├── src/input.css       # Tailwind entry + theme, animations, base rules
├── dist/styles.css     # compiled CSS (gitignored; produced by build)
├── assets/
│   └── hero.webp       # hero illustration, compressed by Luere (4.8 MB → 117 KB)
├── favicon.svg         # teal "L" mark
├── robots.txt          # allows all incl. AI crawlers; links sitemap
├── sitemap.xml
├── llms.txt            # brief written for AI assistants (discovery)
├── SEO.md              # SEO & AI-discovery plan
├── package.json        # build/dev scripts
└── README.md
```

## Develop

```bash
npm install
npm run dev      # watches src/input.css → dist/styles.css
```

Open `index.html` directly, or serve it: `npx serve`.

**Previewing:** open in **Safari**. Safari caches `file://` CSS/JS aggressively —
after a rebuild, hard-reload with **⌘⌥R** ("Reload From Origin") or the new CSS
won't apply. To render without a browser window (e.g. headless), any Chromium
`--headless --screenshot` works; note headless clamps the layout viewport to
~480px, so it can't screenshot true phone widths (the layout itself is fluid).

## Build

```bash
npm run build    # minified dist/styles.css
```

Deploy the folder to any static host (Netlify, Vercel, Cloudflare Pages, GitHub
Pages). `node_modules/` and `dist/` are gitignored; configure the host to run
`npm install && npm run build`, or commit `dist/` if the host only serves files.

## Design system

- **Light, monochrome + one teal accent** (`--color-brand-500: #0f766e`), matching
  the Puuunch family. The teal is drawn from the hero illustration's sky.
- **Type** — Instrument Sans; large, tight tracking, `text-balance` headlines.
- **Components** — pill buttons (`rounded-xl`, teal primary / white-bordered
  secondary), cards `rounded-2xl border-neutral-200`, section rhythm ~py-28.
- **Motion** — scroll-reveal fade-ins, an animated before/after wipe in the hero
  app mock, a heartbeat in the footer. All respect `prefers-reduced-motion`.
- **Buttons get `cursor: pointer`** via a base rule (Tailwind v4 dropped the
  default).

## Content still to wire up (search `TODO` in the source)

- **Production domain** — replace `https://luere.app/` in the canonical, OG tags,
  `sitemap.xml`, `robots.txt`, JSON-LD, and `llms.txt`.
- **Download link** — point the modal's `.dmg` button at the notarized build.
- **Buy me a coffee** — a Stripe Payment Link (footer + modal).
- **Luere Icon Studio** — real URL for the second promo (UTM like Puuunch).
- **OG image** — generate `assets/og.png` (1200×630).

## License / credit

Made by [Dominic Martineau](https://dominicmartineau.com).
