# Deploy Guide — LifeQuestAI

Everything you need to get this site live on the internet, free, with HTTPS, on your own domain.

**Total time:** ~15 minutes
**Total cost:** $0 (until you buy a custom domain — ~$10/yr)

---

## Step 1 — Push to GitHub

### If you don't have a GitHub account yet

1. Go to https://github.com/join and sign up (free).
2. Verify your email.

### Create the repo

1. Go to https://github.com/new
2. **Repository name:** `lifequestai-site` (or whatever you want)
3. **Public** or **Private** — either works with Cloudflare Pages
4. **Do NOT** check "Add a README" — we already have one
5. Click **Create repository**

### Push your files

GitHub will show you commands. Use these two blocks:

**Option A — the easy way (GitHub Desktop app):**
1. Download https://desktop.github.com
2. Sign in
3. File → **Add local repository** → point it at this project folder
4. It'll say "not a git repo" — click **create a repository**
5. **Publish repository** button (top right) → done

**Option B — command line:**
```bash
cd /path/to/this/project
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/lifequestai-site.git
git push -u origin main
```

---

## Step 2 — Deploy to Cloudflare Pages

### Create a Cloudflare account (if you don't have one)

1. Go to https://dash.cloudflare.com/sign-up
2. Verify your email

### Connect GitHub

1. In the Cloudflare dashboard, left sidebar: **Workers & Pages**
2. Click **Create** → **Pages** tab → **Connect to Git**
3. Click **Connect GitHub** → authorize Cloudflare
4. Pick your `lifequestai-site` repo → **Begin setup**

### Configure the build

You'll see a form. Fill it in like this:

| Field | Value |
|---|---|
| **Project name** | `lifequestai` (this becomes `lifequestai.pages.dev`) |
| **Production branch** | `main` |
| **Framework preset** | `None` |
| **Build command** | *(leave blank)* |
| **Build output directory** | `/` |

Click **Save and Deploy**.

⏱ Wait ~60 seconds. You'll see build logs run, then a success screen with your live URL:
**`https://lifequestai.pages.dev`**

That's it. Site is live.

**From now on:** every time you `git push` to `main`, Cloudflare auto-rebuilds and redeploys in about a minute. No extra steps.

---

## Step 3 — Add your own domain (optional)

If you own `lifequestai.com` (or similar):

1. In your Cloudflare Pages project → **Custom domains** tab
2. Click **Set up a custom domain**
3. Enter your domain (e.g. `lifequestai.com` or `www.lifequestai.com`)
4. Cloudflare will tell you whether to:
   - **Option 1:** Change your domain's nameservers to Cloudflare (best — gives you free CDN + security on top)
   - **Option 2:** Add a CNAME record at your current DNS host
5. Follow the on-screen instructions. SSL certificate is issued automatically.

**Don't own a domain yet?** Cheapest reputable registrars:
- https://www.cloudflare.com/products/registrar/ (at-cost pricing, no markup — best option if you're already on Cloudflare)
- https://porkbun.com
- https://www.namecheap.com

---

## Making changes later

1. Edit `index.html` or `styles.css` locally (or in GitHub's web editor)
2. Commit and push:
   ```bash
   git add .
   git commit -m "Updated hero copy"
   git push
   ```
3. Cloudflare rebuilds automatically. Refresh your site in ~60 seconds.

---

## Troubleshooting

**"Build failed" in Cloudflare:**
Check that **Build command** is blank and **Build output directory** is `/` (or empty). This is a plain HTML site — there's nothing to build.

**Site loads but looks broken:**
Make sure `styles.css` is at the repo root, next to `index.html`. The `<link href="styles.css">` in the HTML is a relative path.

**Custom domain says "pending":**
DNS propagation can take up to 24 hours (usually much faster). Grab coffee, come back.

---

## Questions?

Ping me and I'll walk through any step live.
