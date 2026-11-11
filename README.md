# Little Seeds Children's Books — Website

Static website: one `index.html`, images in `images/`. No build step, no server code, no secrets in the files.
Pages use hash links (`#books`, `#terms`, ...), so everything works on GitHub Pages without rewrite rules. Asset paths are relative.

Live site: https://mutabazi3907-jpg.github.io/little-seeds-childrens-books/

## Deploy on GitHub Pages
The site is published by GitHub Pages from the `main` branch (Settings > Pages > Deploy from a branch > `main` > `/ (root)`). Do not commit changes straight to `main`. To release an update:
1. Create a branch (for example `my-update`) and make the changes there. Do not open and re-save images or PDFs in a text editor.
2. Test locally: run `python3 -m http.server` in the folder and open http://localhost:8000/.
3. Open a pull request into `main`, review it, then merge it. The site updates in 1-3 minutes (browsers may cache pages for about 10 minutes, so hard-refresh).
Only public files belong in this repository. Keep print-bleed files, editable sources and internal reports elsewhere.

## Files
| File | Purpose |
|---|---|
| `index.html` | Entire site: 14 views (home, books, resources, parents-educators, church-school, catalogue, sponsor, partnerships, about, founder, mission, contact, privacy, terms), styles, scripts, book catalogue (`BOOKS` list), Privacy and Terms text (`PRIV`, `TERMS`) |
| `images/little-boy.webp`, `little-boy-sm.webp` | Cover, *The Little Boy Who Learned to Share* |
| `images/who-made-everything.webp`, `-sm.webp` | Draft cover preview, *Who Made Everything?* (replace with the final cover) |
| `images/little-bird.webp`, `-sm.webp` | Cover, *The Little Bird Who Lost Her Way Home* |
| `images/joseph-mutabazi.webp` | Founder photo |
| `images/og-image.png` | Social sharing image |
| `images/logo-temporary.png` | TEMPORARY logo crop (462×270). Replace this one file with the original logo; every page uses it. |
| `images/flyers/`, `images/resources/` | Web previews of the flyers, catalogue and kits |
| `downloads/` | Public digital PDFs only (activity pack, partnership kit, catalogue, six flyers). Print-bleed files, editable sources and production reports are NOT stored here |
| `resources/`, `parents-educators/`, `church-school/`, `partnerships/`, `catalogue/` | Small redirect pages so these URLs work and carry their own title and description; they send visitors to the matching `#` view |
| `favicon.svg`, `robots.txt`, `sitemap.xml` | Site icon and search-engine files |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |
| `README.md` | This file (harmless if deleted) |

## Connected services
- **Contact form:** sends to Formspree (`CONFIG.formEndpoint` in `index.html`). The success message appears only after Formspree reports success; otherwise the visitor sees a failure message.
- **Newsletter:** Kit (formerly ConvertKit), inline form, Form ID 10168705, loaded with Kit's script `https://f.convertkit.com/ckjs/ck.5.js` (loaded once). The form is Kit's official embed, styled to match the site. It does not use pop-ups, slide-ins or sticky bars.
- **Fonts:** Google Fonts (external).
- The Privacy Policy and Terms disclose these services. Do not add private API keys to the site.

## Still to complete before the policies are final
- Privacy Policy and Terms are **drafts** pending attorney review. Highlighted [CONFIRM] items and "Attorney review" boxes are unresolved. Add the business mailing address, legal entity details and effective date only when confirmed.
- Replace the *Who Made Everything?* cover with the final high-resolution original when available.

## Maintaining books
Edit the `BOOKS` list in `index.html`. `status` is `Published`, `Coming Soon` or `In Development`. Fill `amazon` only when a book is published and its link is verified. Also update the book's entry in the JSON-LD block near the top of `index.html` and the Amazon links shown elsewhere.

## Downloads and Book 3
The Book 3 activities (Activity and Learning Pack, pages 20–29) have been reviewed against the approved Book 3 manuscript, and the former “awaiting manuscript verification” labels have been removed from the site, the pack and the Partnership Kit. Privacy, Terms and Sponsor wording remain drafts pending attorney review.

## Logo
The logo is a temporary crop. To replace it, overwrite `images/logo-temporary.png` (keep roughly a 462:270 aspect or update the `width`/`height` attributes in `index.html`).
