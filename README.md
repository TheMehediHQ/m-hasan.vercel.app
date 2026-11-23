# m-hasan.vercel.app

> An ultra-fast, modern redirect website built with [Astro](https://astro.build). Automatically redirects visitors from **[m-hasan.vercel.app](https://m-hasan.vercel.app)** to **[mehedi-hasan.me](https://mehedi-hasan.me)**.

[![Live URL](https://img.shields.io/badge/Live%20URL-m--hasan.vercel.app-000000?style=for-the-badge&logo=vercel)](https://m-hasan.vercel.app)
[![Target Destination](https://img.shields.io/badge/Redirects%20To-mehedi--hasan.me-38bdf8?style=for-the-badge)](https://mehedi-hasan.me)
[![GitHub Repository](https://img.shields.io/badge/Repository-TheMehediHQ%2Fm--hasan.vercel.app-blue?style=for-the-badge&logo=github)](https://github.com/TheMehediHQ/m-hasan.vercel.app)

---

## 📌 Project Overview

- **Project Name:** `m-hasan.vercel.app`
- **Repository:** [`TheMehediHQ/m-hasan.vercel.app`](https://github.com/TheMehediHQ/m-hasan.vercel.app)
- **Source URL:** [https://m-hasan.vercel.app](https://m-hasan.vercel.app)
- **Target Destination:** [https://mehedi-hasan.me](https://mehedi-hasan.me)

---

## ⚡ Key Features

1. **Triple-Layer Redirection System**:
   - **Edge / Server-Level 301 Redirect**: Powered by `vercel.json` (for Vercel) and `_redirects` (for Netlify and Cloudflare Pages) for instant, zero-delay HTTP 301 redirection at the edge before any HTML is parsed.
   - **Immediate Client-Side JavaScript**: Executes `window.location.replace()` in the document `<head>` to immediately route users without polluting the browser's Back button history.
   - **HTML `<meta http-equiv="refresh">`**: Fallback mechanism for bots, scrapers, or browser clients with JavaScript disabled.
2. **SEO & Link Equity Preservation**:
   - Includes `rel="canonical"` pointed directly to `https://mehedi-hasan.me/`.
   - Employs `robots: "noindex, follow"` to prevent search engines from treating the redirect domain as duplicate content while passing along page authority.
3. **Catch-All 404 Fallback**:
   - Includes a dedicated `404.astro` page so any requested subpath (e.g., `/about`, `/projects`) automatically redirects to the destination root.
4. **Modern Fallback UI**:
   - Elegant dark-mode interface with a loading spinner and manual destination link in case client redirection is delayed.

---

## 🚀 Local Development

### Prerequisites
- Node.js (`>= 22.12.0`) or [Bun](https://bun.sh)

### Installation & Run

```bash
# Clone the repository
git clone https://github.com/TheMehediHQ/m-hasan.vercel.app.git
cd m-hasan.vercel.app

# Install dependencies
npm install
# or
bun install

# Start the local development server
npm run dev
# or
bun run dev
```

Visit `http://localhost:4321` in your browser to test the redirection.

### Build for Production

```bash
npm run build
# or
bun run build
```

Production static assets will be output to the `dist/` folder.

---

## 🌐 Deployment

### Vercel (Recommended)
1. Push your code to GitHub.
2. Import repository `TheMehediHQ/m-hasan.vercel.app` into [Vercel](https://vercel.com).
3. The framework will be automatically detected as **Astro**.
4. Set the project name / domain to **`m-hasan.vercel.app`**.
5. Deploy. `vercel.json` will automatically manage 301 edge redirects.

### Cloudflare Pages
1. Connect repository in Cloudflare Dashboard under **Workers & Pages** > **Pages**.
2. Build Settings:
   - Framework preset: `Astro`
   - Build command: `npm run build`
   - Output directory: `dist`
3. Deploy. The `_redirects` file automatically handles edge redirection.

### Netlify
1. Import repository into Netlify.
2. Build command: `npm run build`
3. Publish directory: `dist`
4. Deploy.

---

## 📄 License

MIT © [Mehedi Hasan](https://mehedi-hasan.me)
