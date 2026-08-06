# MyApps Download Center — Cloudflare Pages

This folder is ready to deploy as a static site on Cloudflare Pages.

## Option A: Dashboard (no CLI, easiest)
1. Go to https://dash.cloudflare.com → **Workers & Pages** → **Create application** → **Pages** → **Upload assets**.
2. Give the project a name (e.g. `myapps-download-center`).
3. Drag and drop this whole folder (or just `index.html` if you don't need the extras) into the upload area.
4. Click **Deploy site**. Cloudflare will give you a `*.pages.dev` URL immediately.
5. To use your own domain, go to the project → **Custom domains** → add your domain and follow the DNS steps.

## Option B: Wrangler CLI
```bash
npm install -g wrangler
cd myapps-site
wrangler login
wrangler pages deploy . --project-name=myapps-download-center
```
This uploads the folder and gives you a `*.pages.dev` URL. Re-run the same command any time you update `index.html` to redeploy.

## Notes
- `index.html` is the file that was uploaded, renamed to `index.html` (required — Cloudflare Pages serves this as the site root automatically).
- `wrangler.toml` is only needed if you use the CLI (Option B). The dashboard upload (Option A) ignores it.
- This is a static site (HTML/CSS/JS only) — no build step is required, so there's nothing else to configure.
