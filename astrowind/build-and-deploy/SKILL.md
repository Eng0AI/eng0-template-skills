---
name: build-and-deploy
description: Build and deploy this Astro website. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy AstroWind

> **CRITICAL: For Vercel, use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**

## Tech Stack

- Astro 5.x with MDX support
- Tailwind CSS
- TypeScript
- Built-in blog with RSS feed

## Workflow

### 1. Install Dependencies

```bash
npm install
```

### 2. Build

```bash
npm run build
```

Output directory: `dist/`

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

```bash
npm run dev
# Opens at http://localhost:4321
```

## Configuration

Edit `src/config.yaml` to customize:
- Site name, description, and metadata
- Navigation links
- Social media links
- Analytics settings

## Environment Variables

No required environment variables for the base template. Add your own as needed:
- `ANALYTICS_ID` - Google Analytics ID (optional)
