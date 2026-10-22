# canvas

Static pages for [c.mayron.us](https://c.mayron.us). Same look as [mayron.us](https://mayron.us): Inter, Playfair Display, and JetBrains Mono, the same color tokens, navbar, and footer. Styles live in this repo (`STATIC/styles/main.css` is copied from the personal site, and `STATIC/styles/site.css` adds the page layout). Nothing is hotlinked from mayron.us.

mayron.us is hand-written HTML, not a Jekyll or Hugo site. GitHub Pages publishes it from the `main` branch, folder `/`. This repo works the same way. There is no build step. `.nojekyll` tells Pages to serve the files as they are, instead of running Jekyll.

## GitHub Pages

In the repository settings, under **Pages → Build and deployment**:

- **Source:** Deploy from a branch
- **Branch:** `main`
- **Folder:** `/ (root)`

The custom domain is `c.mayron.us` (`CNAME` at the repository root). Point a DNS CNAME record for `c.mayron.us` at `jaredmayron.github.io`, then set that domain in the Pages settings if it is not picked up from the file.

## Add a page

1. Create `your-page-slug/index.html`. Copy the head, navbar, and footer from `blues-2026-10-22/index.html`. Stylesheet, script, and home links stay root-absolute (`/STATIC/...`, `/`).
2. On an event page, keep `<meta name="robots" content="noindex">`. Leave out confirmation codes, order numbers, ticket codes, and flight seat numbers. The page is public.
3. Add a card to the list in `index.html` that links to `/your-page-slug/`.
4. Commit to `main`. Pages serves it at `https://c.mayron.us/your-page-slug/`.
