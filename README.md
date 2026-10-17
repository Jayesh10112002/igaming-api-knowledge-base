# iGaming API Knowledge Base

**Practical, developer-focused guides to casino API integration, slots APIs, live casino, sportsbook technology and scalable iGaming infrastructure — maintained by [Betnex](https://www.betnex.co/).**

- **Website:** https://www.betnex.co/
- **Casino API platform:** https://casinoapi.betnex.co/
- **Games aggregated:** 40,000+ · **Providers:** 300+ · **Live operator sites:** 150+ · **Platform GGR:** flat 13%

This repository is a Jekyll site (GitHub Pages ready). It is educational content, not legal or commercial advice.

## Run locally

Requires Ruby and Bundler:

```bash
bundle install
bundle exec jekyll serve
```

Open http://127.0.0.1:4000/igaming-api-knowledge-base/ in your browser.

## Configure the canonical domain (do this before deploy)

All canonical URLs, Open Graph tags and the sitemap are generated from two values in `_config.yml`. Set them to your real domain:

```yaml
# Option A — GitHub Pages (works out of the box)
url: "https://jayesh10112002.github.io"
baseurl: "/igaming-api-knowledge-base"

# Option B — custom domain (recommended for SEO)
url: "https://kb.betnex.co"
baseurl: ""
```

For a custom domain, also add a `CNAME` file at the repo root containing the domain (e.g. `kb.betnex.co`) and point DNS at GitHub Pages.

Search Console / Bing verification codes go in `_config.yml` (`google_site_verification`, `bing_site_verification`).

## Publish with GitHub Pages

1. Push to the `main` branch.
2. In GitHub, open **Settings → Pages** and set the source to **GitHub Actions**.
3. The included workflow (`.github/workflows/pages.yml`) builds and deploys the site.
4. After the first deploy, verify the canonical URL, `robots.txt` and `sitemap.xml` on the live domain, then submit the sitemap in Google Search Console.

## Where the content lives

- `index.md` — home page.
- `about.md`, `betnex.md` — publisher and Betnex services/data pages.
- `casino-api/`, `slots-api/`, `live-casino/`, `sportsbook/`, `engineering/`, `resources/` — topic guides.
- Each folder has an `index.md` category page plus one or more article pages.

## Editing conventions

- Keep one search intent per article; use descriptive `##` headings and internal links.
- Article front matter: `layout: article`, `title`, `description`, `category`, `permalink`, `date`.
- Update `last_modified_at` in an article's front matter when you materially change it.
- Never commit credentials, private provider documentation, customer data or production source code.

## SEO features included

- `jekyll-seo-tag` (titles, canonical, Open Graph, Twitter cards), `jekyll-sitemap`, `jekyll-feed`.
- JSON-LD: Organization + WebSite sitewide; Article + BreadcrumbList on guides.
- Per-article table of contents, reading time, breadcrumbs and semantic headings.
- Accessible, responsive UI with a Betnex-branded design system (`assets/css/main.css`).
