# Little Seeds Children's Books — Website

Static website (one `index.html`, images in `images/`). No build step, no server code, no secrets.
Pages use hash links (`#books`, `#terms`, ...), so everything works on GitHub Pages without rewrite rules.
All asset paths are relative, so the site works at a project URL (`https://USER.github.io/REPO/`) and at a custom domain.

## Deploy on GitHub Pages
1. Create a GitHub repository (for example `little-seeds-site`).
2. Upload the CONTENTS of this folder to the repository root, so `index.html` sits at the top level (not inside a subfolder). Include `images/` and the hidden `.nojekyll` file.
   - Web: Add file > Upload files > drag everything in > Commit.
   - Or git: `git init && git add . && git commit -m "Initial site" && git branch -M main && git remote add origin <repo-url> && git push -u origin main`
3. Repository Settings > Pages > Build and deployment: Source = "Deploy from a branch", Branch = `main`, Folder = `/ (root)` > Save.
4. Wait 1-3 minutes. The site appears at `https://USER.github.io/REPO/`.
5. Open it and check: all nine pages, each book page, the Amazon button on *The Little Boy Who Learned to Share*, dark mode, and phone width.

## Custom domain (optional)
1. Settings > Pages > Custom domain: enter your domain (e.g. `www.yourdomain.com`) > Save. GitHub creates a `CNAME` file in the repo.
2. At your domain registrar, add DNS records: for `www`, a CNAME to `USER.github.io`; for an apex domain, A records to 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153 (confirm current values in GitHub's docs).
3. When the certificate is ready, tick "Enforce HTTPS".

## Files
| File | Purpose |
|---|---|
| `index.html` | Entire site: 9 pages, styles, scripts, book catalogue (`BOOKS` list), Privacy and Terms text (`PRIV`, `TERMS`) |
| `images/little-boy.webp`, `little-boy-sm.webp` | Cover, *The Little Boy Who Learned to Share* (full and thumbnail) |
| `images/who-made-everything.webp`, `-sm.webp` | Cover preview, *Who Made Everything?* (draft/low-res, replace with final) |
| `images/little-bird.webp`, `-sm.webp` | Draft cover, *The Little Bird Who Lost Her Way Home* |
| `images/joseph-mutabazi.webp` | Founder photo |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |
| `README.md` | This file (may be deleted from the repo; harmless if left) |

## Still disconnected / to configure
- **Contact form and newsletter are NOT connected.** Submissions go nowhere, and the site tells visitors so. To connect: in `index.html` find `var CONFIG={formEndpoint:"",newsletterEndpoint:""};` and paste public endpoint URLs (e.g. a Formspree form URL; a Kit or Mailchimp form-action URL). The "not connected" notices hide automatically once set. Never paste private API keys.
- **Fonts:** loaded from Google Fonts (external). The Privacy Policy discloses this; self-hosting is optional and needs attorney/owner decision.
- **No sitemap.xml, robots.txt, social-sharing image or favicon** are included (none were supplied or approved). Add them after the public URL is known; add `<meta property="og:image">` pointing to the full URL of an approved image.
- **Privacy Policy and Terms are drafts** with highlighted [CONFIRM] and attorney-review items. Fill the website address and mailing address, and have an attorney review before launch.
- Social media links are not included (none supplied).
- Replace the *Who Made Everything?* cover with the final high-resolution original when available.

## Maintaining
Add books by adding an entry to the `BOOKS` list in `index.html`; change `status` (Published / Coming Soon / In Development) and fill `amazon` only when a book is published. Change a cover by replacing the image file and updating `cover` / `coverSm`.
