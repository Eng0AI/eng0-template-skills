---
name: setup
description: Set up the Designer Portfolio template in the current directory. Use when initializing a new project from this template.
---

# Setup Designer Portfolio Template

This skill sets up a stunning portfolio landing page with smooth scroll animations using Locomotive Scroll, GSAP, and Framer Motion.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm or npm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/awwwards-landing-page-template.git .
```

If the directory is not empty, clone to a temp directory and move files:

```bash
git clone --depth 1 https://github.com/Eng0AI/awwwards-landing-page-template.git _temp_template
mv _temp_template/* _temp_template/.* . 2>/dev/null || true
rm -rf _temp_template
```

### 2. Remove Git History (Optional - for fresh start)

```bash
rm -rf .git
git init
```

### 3. Install Dependencies

```bash
pnpm install
# or
npm install
```

### 4. Verify Setup

```bash
pnpm build
# or
npm run build
```

## Tech Stack

- **Framework**: Next.js
- **React**: React
- **Animation**: Locomotive Scroll, GSAP, Framer Motion
- **Package Manager**: pnpm (recommended) or npm

## Next Steps

After setup, you can:
1. Run `pnpm dev` to start development server (localhost:3000)
2. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
