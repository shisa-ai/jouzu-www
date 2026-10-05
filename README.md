# jouzu-www

Source for [jouzu.dev](https://jouzu.dev), the landing page for [Jouzu](https://github.com/shisa-ai/jouzu). Built with [Astro](https://astro.build/).

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
| `src/pages/index.astro` | Landing page |
| `src/layouts/Base.astro` | HTML shell and meta tags |
| `src/components/BrailleLogo.astro` | Jouzu braille mark as SVG; glyphs and gradient mirror `packages/cli/src/presentation.ts` in the jouzu repo |
| `src/styles/global.css` | Tokyo Night palette and base styles |
| `public/favicon.svg` | Copied from `packaging/windows/jouzu.svg` in the jouzu repo |

## Deploy

Pushing to `main` runs `.github/workflows/deploy.yml`, which builds the site and publishes it to GitHub Pages.

The custom domain is set in the repo's Pages settings rather than a `CNAME` file. DNS is at Namecheap: four `A` records on `@` pointing at GitHub Pages and a `CNAME` for `www` pointing at `shisa-ai.github.io`.
