---
name: build-and-deploy
description: Build and deploy this Next.js admin dashboard application. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy TailAdmin Next.js

> **CRITICAL: For Vercel, use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**

## Tech Stack

- Next.js 16.x with React 19
- TypeScript
- Tailwind CSS v4
- ApexCharts for data visualization

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

**Vercel (Recommended for Next.js):**

```bash
vercel pull --yes -t $VERCEL_TOKEN
vercel build --prod -t $VERCEL_TOKEN
vercel deploy --prebuilt --prod --yes -t $VERCEL_TOKEN
```

**Netlify:**

```bash
netlify deploy --prod
```

## Development

```bash
npm run dev
# Opens at http://localhost:3000
```

## Environment Variables

No required environment variables for the base template. Add your own as needed for API integrations.
