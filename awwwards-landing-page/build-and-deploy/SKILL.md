---
name: build-and-deploy
description: Build and deploy this Next.js landing page application. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy Awwwards Landing Page

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
# Deploy (Next.js is automatically detected)
netlify deploy --prod
```

## Critical Notes

- **VERCEL PREBUILT MODE IS MANDATORY:** Always use `vercel build --prod` followed by `vercel deploy --prebuilt --prod`. Never use `vercel --prod` or `vercel deploy --prod` without `--prebuilt` flag.
- **Static Site:** This is a static Next.js site - no environment variables needed
- **No Dev Server:** Never run `npm run dev` in VM environment
