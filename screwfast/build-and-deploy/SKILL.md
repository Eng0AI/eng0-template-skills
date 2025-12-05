---
name: build-and-deploy
description: Build and deploy this Astro application. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy ScrewFast

> **CRITICAL: For Vercel, use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**

## Tech Stack
- **Framework**: Astro 5 with Starlight docs
- **Styling**: Tailwind CSS 4 + Preline UI
- **Animations**: GSAP + Lenis smooth scroll
- **Build Output**: `dist/` directory

## Workflow

### 1. Install Dependencies
```bash
npm install
```

### 2. Build
```bash
npm run build
```

This runs `astro check && astro build && node process-html.mjs` which:
- Type checks the project
- Builds the Astro site
- Minifies HTML output

### 3. Deploy

**Vercel:**
```bash
vercel pull --yes -t $VERCEL_TOKEN
vercel build --prod -t $VERCEL_TOKEN
vercel deploy --prebuilt --prod --yes -t $VERCEL_TOKEN
```

**Netlify:**
```bash
netlify deploy --prod --dir=dist
```

## Development

Start local dev server:
```bash
npm run dev
```

Preview production build:
```bash
npm run preview
```
