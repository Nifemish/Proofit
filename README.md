# Proofit - Deploy from GitHub to Netlify or Vercel

This is a single-page React app ready for deployment.

---

## Files Included

| File | Purpose |
|------|---------|
| `index.html` | The main app (single-file React SPA) |
| `_redirects` | Netlify SPA fallback rule |
| `netlify.toml` | Alternative Netlify config with rewrite rule |
| `vercel.json` | Vercel SPA rewrite rule |

---

## Deploy to Netlify (from GitHub)

### Option 1: Using `_redirects` file

1. Push this folder to a **GitHub repository**.
2. Go to [netlify.com](https://netlify.com) → Add new site → Import from GitHub.
3. Select your repo. Netlify will auto-detect the `_redirects` file.
4. Deploy.

### Option 2: Using `netlify.toml`

Same steps as above — the `netlify.toml` already contains the rewrite rule. You can delete `_redirects` if you prefer `netlify.toml`.

---

## Deploy to Vercel (from GitHub)

1. Push this folder to a **GitHub repository**.
2. Go to [vercel.com](https://vercel.com) → Add New Project → Import from GitHub.
3. Select your repo. Vercel will auto-detect the `vercel.json` file.
4. Deploy.

---

## Important Notes

- **SPA Routing**: The rewrite rules ensure client-side routes like `/login`, `/dashboard`, `/templates`, `/preview/:id`, and `/admin` work correctly on refresh or direct access.
- **No Build Step Required**: This is a static single-file app — no build command is needed. Both Netlify and Vercel will serve it as static HTML.
- **API Endpoints**: The app calls `/api/healthz` and `/api/auth/logout`. These do not exist in static hosting and will return 404. The app handles this gracefully (shows "Offline" status, logout clears local state).

---

## Push to GitHub

```bash
cd proofit-github
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/proofit.git
git push -u origin main
```

Replace `YOUR_USERNAME/proofit` with your actual GitHub username and repo name.