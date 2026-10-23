# jouzu-www

Source for [jouzu.dev](https://jouzu.dev). The site is a client-side redirect to the [Jouzu page on the Shisa AI Platform](https://platform.shisa.ai/jouzu). Built with [Astro](https://astro.build/).

## Develop

```bash
npm install
npm run dev      # http://localhost:4321
npm run build    # outputs to dist/
npm run preview  # serve the built site
```

Requires Node.js 22.12 or newer (CI uses the version in `.nvmrc`).

## Layout

| Path | Purpose |
| --- | --- |
| `src/pages/index.astro` | Redirect page: inline `window.location.replace` plus a `<meta http-equiv="refresh">` fallback and a manual link for clients that block both |
| `src/styles/global.css` | Tokyo Night palette and base styles |
| `public/favicon.svg` | Copied from `packaging/windows/jouzu.svg` in the jouzu repo |

The earlier landing page (braille mark, install command, download link) is preserved in git history at commit `a3a04bd` if it needs to come back.

## Deploy

Pushing to `main` runs `.github/workflows/deploy.yml`, which builds the site and publishes it to GitHub Pages.

The custom domain is set in the repo's Pages settings rather than a `CNAME` file. DNS is at Namecheap: four `A` records on `@` pointing at GitHub Pages and a `CNAME` for `www` pointing at `shisa-ai.github.io`.
