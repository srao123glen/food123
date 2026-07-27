# food123.ai — static copy

A one-time static snapshot of the live Shopify storefront at https://food123.ai,
taken so the design can be edited and previewed on GitHub Pages.

Published at https://srao123glen.github.io/food123/ — every push to `main`
redeploys it via `.github/workflows/pages.yml`.

This is **not** a live mirror. Nothing here syncs with Shopify. Once the snapshot
was taken, this copy became fully independent — all further changes happen here.

## What works

Everything that is presentation: layout, styling, imagery, fonts, navigation
between the captured pages, sliders/carousels, menus.

## What does not work

The storefront's dynamic half was served by Shopify, so it has no backend here:

- Cart, checkout, and any "Add to cart" button
- Customer accounts / login
- Search and predictive search
- Newsletter signup and contact form submission
- Currency / country switching

These are safe to leave broken while iterating on design, or to replace with
whatever the new site should do.

## Layout

```
index.html          home page
collections/        collection (category) pages
products/           product detail pages
pages/              about, FAQs, knowledge centre, policies, contact
policies/           Shopify-generated policy pages
cdn/                theme CSS/JS, images, fonts
.nojekyll           tells GitHub Pages to serve files/dirs starting with "_"
```

Asset filenames keep Shopify's cache-busting version string with `?` rewritten
to `@` (e.g. `base.css@v=1309655…css`), so they resolve as plain static files.

## Editing

Plain HTML and CSS — edit directly. Shared chrome (header, footer, nav) was
inlined into every page by the snapshot, so a change to the header must be
applied across the HTML files, or the pages refactored onto a template/static
site generator first.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```
