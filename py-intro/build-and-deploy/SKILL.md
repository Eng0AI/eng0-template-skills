---
name: build-and-deploy
description: Build and deploy this Slidev presentation. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy Python Intro Slides

> **CRITICAL: For Vercel, use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**

## Tech Stack
- Slidev (Vue-based presentation framework)
- Python Runner addon for interactive code execution
- npm package manager
- Output directory: `dist`

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

To run locally:
```bash
npm run dev
```

This will start the Slidev server and open the presentation in your browser.

## Special Features

This template includes:
- `slidev-addon-python-runner` - Interactive Python code execution in slides
- `slidev-addon-rabbit` - Additional Slidev features
- Multiple themes (apple-basic, bricks, penguin)
