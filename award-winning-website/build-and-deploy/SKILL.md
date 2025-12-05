---
name: build-and-deploy
description: Build and deploy this React + Vite award-winning website. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy Award-Winning Website

> **CRITICAL: For Vercel, you MUST use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**
> Do NOT use `vercel --prod` or `vercel deploy --prod` directly - these will fail due to Git author permission issues in VM environments.

## Workflow

### 1. Install Dependencies

```bash
npm install
```

### 2. Build

```bash
npm run build
```

This creates a production build in the `dist/` directory.

### 3. Deploy

**Vercel:**

All vercel CLI commands require `-t <token>` or `--token <token>` for authentication.

```bash
# Pull project settings (also links project, creates .vercel/project.json)
vercel pull --yes -t $VERCEL_TOKEN

# Build locally for production
vercel build --prod -t $VERCEL_TOKEN

# Deploy prebuilt
vercel deploy --prebuilt --prod --yes -t $VERCEL_TOKEN
```

**Netlify:**

```bash
# Deploy (dist is the output directory for Vite)
netlify deploy --prod --dir=dist
```

## Critical Notes

- **VERCEL PREBUILT MODE IS MANDATORY:** Always use `vercel build --prod` followed by `vercel deploy --prebuilt --prod`. Never use `vercel --prod` or `vercel deploy --prod` without `--prebuilt` flag.
- **Static Site:** This is a static React site with no backend - no environment variables needed
- **Output Directory:** Vite outputs to `dist/` directory
- **No Dev Server:** Never run `npm run dev` in VM environment
