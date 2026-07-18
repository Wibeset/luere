# Luere website

Marketing microsite for **Luere**, the free macOS image compressor. Static
HTML + Tailwind CSS v4. This is the direct-download funnel hub (Puuunch
cross-promo, email capture, attribution).

## Develop

```bash
npm install
npm run dev      # rebuilds dist/styles.css on change
```

Then open `index.html` in a browser (any static server works too, e.g.
`npx serve`).

## Build for production

```bash
npm run build    # minified dist/styles.css
```

Deploy the folder (`index.html` + `dist/`) to any static host — Netlify,
Vercel, Cloudflare Pages, GitHub Pages. `node_modules/` and `dist/` are
gitignored; the host should run `npm install && npm run build`.

## Still to wire up (search the HTML for `TODO`)

- **Download link** — point the `.dmg` button at the notarized build.
- **Email form** — set the `<form action>` to your provider.
- **Puuunch** — confirm the real URL and pitch (UTM params already set).
- **Tip link** — set the "Buy me a coffee" URL, or remove it.
- **Hero image** — optionally swap the CSS mock for a real screenshot.
