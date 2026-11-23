# Redicti-m-hasan

An ultra-fast, robust redirect website built with [Astro](https://astro.build). Once deployed, any visitor will automatically and instantly be redirected to [https://mehedi-hasan.me](https://mehedi-hasan.me).

---

## ⚡ Features (কি কি সুবিধা আছে)

1. **3-Layer Redirection**:
   - **Edge / Server-level 301 Redirect**: Via `_redirects` (Netlify, Cloudflare Pages) and `vercel.json` (Vercel) for instant HTTP 301 redirection without waiting for HTML to load.
   - **Immediate Client-side JavaScript**: Uses `window.location.replace()` in the `<head>` so the browser doesn't push a dummy history state (preserves the Back button).
   - **HTML `<meta http-equiv="refresh">`**: Fallback for browsers or bots with JavaScript disabled.
2. **SEO Friendly**:
   - `rel="canonical"` pointed directly to `https://mehedi-hasan.me/`.
   - `robots: "noindex, follow"` prevents search engine duplicate indexing while preserving link equity.
3. **Catch-All 404 Fallback**:
   - `404.html` also redirects to `https://mehedi-hasan.me/` (if someone visits `/anything`).
4. **Clean Fallback UI**:
   - Modern dark mode card with spinner and direct clickable link if the browser delays redirection.

---

## 🚀 How to Run Locally (লোকালি টেস্ট করার নিয়ম)

```bash
# Using bun:
bun run dev

# Or using npm:
npm run dev
```

Build for production:
```bash
bun run build
# Or:
npm run build
```
The static output will be created inside the `dist/` directory.

---

## 🌐 Deployment Options (যেখানে খুশি হোস্ট করতে পারেন)

### 1. Vercel (Recommended)
1. Push this repository to GitHub.
2. Go to [vercel.com](https://vercel.com) -> **Add New Project**.
3. Import this repository.
4. Framework Preset will be automatically detected as **Astro**.
5. Click **Deploy**. (`vercel.json` handles instant 301 redirect).

### 2. Cloudflare Pages
1. Push to GitHub.
2. In Cloudflare Dashboard, go to **Workers & Pages** -> **Create application** -> **Pages**.
3. Connect your repository.
4. Build settings:
   - Framework preset: `Astro`
   - Build command: `npm run build`
   - Build output directory: `dist`
5. Click **Save and Deploy**. (The `_redirects` file handles edge 301 redirect).

### 3. Netlify
1. Go to [netlify.com](https://netlify.com) -> **Add new site** -> **Import an existing project**.
2. Select this repository.
3. Build command: `npm run build`
4. Publish directory: `dist`
5. Click **Deploy**.

### 4. GitHub Pages / Static Hosting (cPanel / S3 / Apache / Nginx)
- Run `npm run build` or `bun run build`.
- Upload the contents of the `dist/` folder directly to your hosting / webroot.
