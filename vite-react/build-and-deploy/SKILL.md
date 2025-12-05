---
name: build-and-deploy
description: Build and deploy this React + Vite application. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy React + Vite

> **CRITICAL: For Vercel, use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**

## Tech Stack

- **Framework**: React 19
- **Build Tool**: Vite 7
- **Language**: TypeScript
- **Package Manager**: npm
- **Output**: `dist` directory
- **Port**: 5173

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

**Vercel (Recommended):**

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

```bash
npm run dev
```

Opens at http://localhost:5173

## Notes

- TypeScript compilation runs before build (`tsc -b && vite build`)
- ESLint configured with React hooks and refresh plugins
- Hot Module Replacement (HMR) enabled in development
