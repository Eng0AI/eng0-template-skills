---
name: build-and-deploy
description: Build and deploy this Next.js portfolio application. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy Portfolio

> **CRITICAL: For Vercel, use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**

## Tech Stack

- Next.js 14
- React 18
- Tailwind CSS
- Framer Motion
- MDX for blog content
- shadcn/ui components

## Workflow

### 1. Install Dependencies

```bash
pnpm install
```

### 2. Build

```bash
pnpm build
```

### 3. Deploy

**Vercel (Recommended):**

```bash
vercel pull --yes -t $VERCEL_TOKEN
vercel build --prod -t $VERCEL_TOKEN
vercel deploy --prebuilt --prod --yes -t $VERCEL_TOKEN
```

**Netlify:**

```bash
netlify deploy --prod --dir=.next
```

## Configuration

The portfolio content is stored in the `content/` directory. Edit the MDX files to customize your portfolio content.

## Environment Variables

No environment variables required for basic deployment.
