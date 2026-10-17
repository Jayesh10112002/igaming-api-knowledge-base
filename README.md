# iGaming API Knowledge Base

A public technical knowledge base covering casino API aggregation, slots APIs, live casino integration, sportsbook technology, wallet callbacks, and iGaming infrastructure.

Maintained by Betnex: [www.betnex.co](https://www.betnex.co/) · [Casino API platform](https://casinoapi.betnex.co/)

> Educational content only. Provider/game availability, currencies, commercial terms, licensing, and market access vary by provider and jurisdiction. Verify requirements before launch.

## Run locally

Requires Ruby and Bundler:

```bash
bundle install
bundle exec jekyll serve
```

Open `http://127.0.0.1:4000`.

## Publish with GitHub Pages

1. Create a **public** repository named `igaming-api-knowledge-base`.
2. Upload the contents of this ZIP to the repository root.
3. Edit `_config.yml`: replace `https://YOUR-USERNAME.github.io` with your GitHub Pages origin and verify `baseurl`.
4. In GitHub, open **Settings → Pages** and enable GitHub Actions deployment if needed.
5. The included workflow builds and deploys the Jekyll site when you push to `main`.

For a project repository, `baseurl` should be `/igaming-api-knowledge-base`. For a user/organization site, use an empty `baseurl`. Update `robots.txt` with the actual sitemap URL.

## Content standards

Write for developers and operators, not search engines alone. Verify examples against your actual API/database versions. Never commit credentials, private provider documentation, customer data, or production source code. Keep commercial claims accurate and contextual.
