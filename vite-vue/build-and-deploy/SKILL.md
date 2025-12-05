---
name: build-and-deploy
description: Build and deploy this Vue + Vite application. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy Vue + Vite

> **CRITICAL: For Vercel, use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**

## Tech Stack

- **Framework**: Vue 3.5
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

- Vue TypeScript compilation runs before build (`vue-tsc -b && vite build`)
- Single File Components (SFC) with `<script setup>` syntax
- Hot Module Replacement (HMR) enabled in development
