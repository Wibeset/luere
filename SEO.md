# SEO & AI-discovery plan — Luere

Goal: rank for image-compression intent on macOS **and** be accurately
summarized by AI assistants (ChatGPT, Claude, Perplexity, Google AI). The site
is also a funnel to the maker's other projects (Puuunch, Luere Icon Studio), so
being *findable* matters as much as *ranking*.

> Replace the placeholder domain `https://luere.app/` everywhere before launch
> (canonical, OG tags, `sitemap.xml`, `robots.txt`, JSON-LD, `llms.txt`).

## Done (in this repo)

- **Semantic HTML** — one `<h1>`, section `<h2>`s, real `<a>`/`<button>`.
- **Meta** — descriptive `<title>` + `<meta description>`, `canonical`,
  `theme-color`, `author`, `robots` (`max-image-preview:large`).
- **Open Graph + Twitter card** — title, description, url, image, `og:site_name`.
- **JSON-LD structured data** — `SoftwareApplication` (free offer, feature list,
  macOS, maker) so search engines and AI agents get machine-readable facts.
- **`robots.txt`** — allows all, explicitly welcomes AI crawlers (GPTBot,
  ClaudeBot, PerplexityBot, Google-Extended), links the sitemap.
- **`sitemap.xml`** — the home URL.
- **`llms.txt`** — a concise, structured brief written *for LLMs*: what Luere is,
  key facts, features, links. This is the emerging convention for AI discovery.
- **`favicon.svg`**, fast static page, mobile-friendly, no render-blocking JS.

## To do — SEO

1. **Domain & hosting** — pick the domain, deploy over HTTPS, set the canonical
   everywhere. Submit the site to Google Search Console & Bing Webmaster Tools;
   submit `sitemap.xml`.
2. **OG image** — create a real `assets/og.png` (1200×630) — hero art + wordmark
   + tagline. Currently referenced but not yet generated.
3. **Self-host the font** — move Instrument Sans local (perf + privacy + no
   render dependency); improves Core Web Vitals (LCP).
4. **Performance** — the hero image is already WebP (117 KB); add width/height
   or `aspect-ratio` to reserve space (CLS), and `loading="eager"`/`fetchpriority`
   on the hero, `loading="lazy"` on below-the-fold images.
5. **Content depth** — a single landing page ranks thin. Add a few focused pages
   that match real queries: "compress images on Mac", "convert HEIC to JPEG",
   "WebP vs AVIF", "reduce image file size without losing quality". Each targets
   a keyword and links back to download. This is the biggest ranking lever.
6. **Internal linking & FAQ** — add an FAQ section with `FAQPage` JSON-LD (rich
   results) answering real questions (formats, privacy, price, requirements).

## To do — AI-agent discovery

1. **Keep `llms.txt` current** — it's the single best lever for accurate AI
   summaries. Update it whenever features/price/links change.
2. **Consistent facts everywhere** — the same claims in `llms.txt`, JSON-LD, and
   visible copy. AI models cross-check; contradictions get dropped.
3. **Structured data breadth** — add `Organization`/`Person` for the maker and,
   once the FAQ exists, `FAQPage`. Consider `SoftwareApplication.softwareVersion`
   and `datePublished` at release.
4. **Off-site presence** — AI answers lean on third-party mentions. Get listed on
   directories (Product Hunt, alternativeto.net, Mac app roundups) and encourage
   a few reviews/blog mentions. This shapes what assistants say more than on-site
   tags do.
5. **Don't block AI crawlers** — `robots.txt` already allows them; keep it that
   way (they are the funnel of the future).

## Measurement

- Search Console (impressions/clicks/queries), Bing Webmaster.
- Privacy-friendly analytics (Plausible/Fathom) for traffic + download clicks.
- Attribution: outbound links to Puuunch / Luere Icon Studio already carry UTM
  params — watch those in the destination project's analytics.
- Periodically *ask the assistants* ("What is Luere?") and check the summary
  matches `llms.txt`; fix drift there.
