# makerrunbook.com: static landing site

Plain HTML and CSS, no build step. Serve from the repository root (or `/docs`) with GitHub Pages.

## Deploy
1. Push the contents of this folder to a repo, e.g. `makerrunbook-site`. The `CNAME` and `.nojekyll` files must be at the root.
2. Go to repo **Settings → Pages**, choose **Deploy from a branch** and pick `main` with `/ (root)`. Set the custom domain to `makerrunbook.com`.
3. Add these records in Cloudflare DNS for makerrunbook.com. Check them against GitHub's "Managing a custom domain" docs before you add them.
   - `A @` → 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - `AAAA @` → 2606:50c0:8000::153, 2606:50c0:8001::153, 2606:50c0:8002::153, 2606:50c0:8003::153
   - `CNAME www` → `<github-username>.github.io`
   - Set them to **DNS only** (grey cloud) until GitHub has issued the certificate. Then turn on **Enforce HTTPS** in Pages. If you switch the Cloudflare proxy on afterwards, use SSL mode **Full**.
4. Optional: verify the domain under GitHub **Settings → Pages → Verified domains**, which adds a TXT record.

## TODOs before launch
- `index.html`, under `TODO(beehiiv)`: replace the placeholder `<form>` with the beehiiv embed and delete the placeholder `<script>` at the bottom.
- `index.html`, under `TODO(gumroad)` (×4): replace `href="#signup"` on each "notify me" button with its Gumroad link when the products are live.
- `assets/print-business-outage-checklist.pdf` is the rebranded lead magnet. Its source is in `../print-business-outage-checklist.html`.
