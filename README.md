# Little Seeds Children's Books — Website

Static website: one `index.html`, images in `images/`. No build step, no server code, no secrets in the files.
Pages use hash links (`#books`, `#terms`, ...), so everything works on GitHub Pages without rewrite rules. Asset paths are relative.

Live site: https://mutabazi3907-jpg.github.io/little-seeds-childrens-books/

## Deploy on GitHub Pages
The repository is already set up (Settings > Pages > Deploy from a branch > `main` > `/ (root)`). To release an update:
1. In the repository, choose Add file > Upload files.
2. Drag the changed files straight from Finder or File Explorer. Do not open and re-save them in a text editor.
3. Commit directly to `main`. The site updates in 1-3 minutes (the browser may cache pages for about 10 minutes, so hard-refresh).

## Files
| File | Purpose |
|---|---|
| `index.html` | Entire site: 9 pages, styles, scripts, book catalogue (`BOOKS` list), Privacy and Terms text (`PRIV`, `TERMS`) |
| `images/little-boy.webp`, `little-boy-sm.webp` | Cover, *The Little Boy Who Learned to Share* |
| `images/who-made-everything.webp`, `-sm.webp` | Draft cover preview, *Who Made Everything?* (replace with the final cover) |
| `images/little-bird.webp`, `-sm.webp` | Cover, *The Little Bird Who Lost Her Way Home* |
| `images/joseph-mutabazi.webp` | Founder photo |
| `images/og-image.png` | Social sharing image |
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
