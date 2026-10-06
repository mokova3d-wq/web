# Mokova3D — JSON Dynamic Edition

This package uses JSON as the site's data layer. The public website reads products, categories, gallery, reviews, FAQ, pages and site configuration from JSON, with an embedded fallback so the site still works when opened directly from a local folder.

## Admin workflow
1. Open `admin.html`.
2. Default password: `Mokova@1234`.
3. Edit/save data in Admin. Changes are stored in this browser as a local draft.
4. Use **Publish / Backup** to download JSON or publish JSON directly to GitHub using a GitHub token.
5. After the JSON files are committed to the GitHub Pages repository, the public website reads the updated JSON.

## What is dynamic
- Products, categories, gallery, reviews, FAQ and pages are data-driven.
- Homepage featured products are driven by `products.json`.
- Category navigation is driven by `categories.json`.
- Product details and product galleries are driven by `products.json`.
- Gallery filters are driven by `gallery.json` + `categories.json`.
- About/Contact/Shipping/Returns/Privacy/Terms are driven by `pages.json`.
- Homepage/SEO/WhatsApp/announcement data are driven by `site-config.json`.

## GitHub Pages limitation
A browser cannot securely overwrite files on GitHub Pages by itself. Therefore a JSON-only site cannot make a saved Admin change live on the server without either:
- publishing the JSON files to GitHub (the built-in Publish tools can do this), or
- adding a backend/database later.

Customer review submissions are kept as a browser-local queue and can be imported into Admin. The form also prepares the review for WhatsApp moderation. A central customer-submission database requires a backend.
