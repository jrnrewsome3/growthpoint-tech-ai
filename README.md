# LifeQuestAI — Landing Page

Marketing landing page for LifeQuestAI. Helps small businesses choose the right Microsoft 365, Copilot, and AI package.

## Stack

Plain static HTML + CSS. No build step, no dependencies.

- `index.html` — the page
- `styles.css` — all styling
- `image_slot.js` — optional drag-and-drop image placeholder component (not currently in use)

## Local preview

Just open `index.html` in any browser. That's it.

Or, if you want a local server:

```bash
# Python
python3 -m http.server 8000

# Node
npx serve .
```

Then visit http://localhost:8000

## Deploy — Cloudflare Pages

1. Push this repo to GitHub.
2. Go to https://dash.cloudflare.com → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
3. Pick this repo.
4. Build settings:
   - **Framework preset:** None
   - **Build command:** *(leave blank)*
   - **Build output directory:** `/` *(or leave blank)*
5. Click **Save and Deploy**.

You'll get a free `*.pages.dev` URL in about 60 seconds. Every push to `main` redeploys automatically.

## Custom domain

In the Pages project → **Custom domains** → **Set up a custom domain** → enter your domain. Cloudflare handles the DNS and SSL for you.

## License

© 2026 LifeQuestAI. All rights reserved.
