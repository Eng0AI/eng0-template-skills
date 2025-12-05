---
name: build-and-deploy
description: Build and deploy this React admin dashboard. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy Mantis React Admin

> **CRITICAL: For Vercel, use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**

## Tech Stack
- **Framework**: React 19 with Vite 7
- **UI Library**: Material UI v7 (MUI)
- **Styling**: Emotion CSS-in-JS
- **Routing**: React Router v7
- **State**: SWR for data fetching
- **Build Output**: `dist/` directory

## Workflow

### 1. Install Dependencies
```bash
yarn install
```

### 2. Build
```bash
yarn build
```

This runs `vite build` which creates an optimized production build in `dist/`.

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
yarn start
```

Preview production build:
```bash
yarn preview
```

## Linting

```bash
yarn lint        # Check for issues
yarn lint:fix    # Auto-fix issues
yarn prettier    # Format code
```
