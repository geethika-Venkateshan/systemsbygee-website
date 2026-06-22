# Systems by Gee — Website

Astro static site. Built for SEO and AEO (semantic HTML, meta + Open Graph, JSON-LD schema, auto sitemap).

## Pages
- `/` Home
- `/about/`
- `/services/`
- `/case-studies/`
- `/blog/` and `/blog/why-your-ghl-setup-is-costing-you-clients/`

## Run locally
```
cd website
npm install
npm run dev
```
Open the URL it prints (usually http://localhost:4321).

## Build
```
npm run build
```
Output goes to `dist/`.

## Deploy to Netlify (free)
1. Push this `website` folder to a GitHub repo.
2. In Netlify, "Add new site" and connect the repo. Settings are read from `netlify.toml` (build `npm run build`, publish `dist`).
3. Newsletter signups are captured with Netlify Forms (free). They show up under Site settings > Forms.
4. Point your domain (registered at Cloudflare) at Netlify: in Netlify add the custom domain, then in Cloudflare DNS add the records Netlify gives you (or use Netlify DNS).

## Notes
- Brand tokens (colours, fonts) live in `src/styles/global.css`.
- SEO/meta/schema is handled in `src/components/BaseHead.astro` and per-page `jsonLd`.
- The `preview-*.html` files are standalone previews for quick viewing. They are not part of the Astro build and can be deleted before deploy.
- Replace `/og-default.jpg` with a real Open Graph image (1200x630) and add brand photos when ready.
- No em dashes anywhere in the copy, by design.
