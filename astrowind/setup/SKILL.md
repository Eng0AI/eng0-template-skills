---
name: setup
description: Set up the AstroWind Landing Page template in the current directory. Use when initializing a new project from this template.
---

# Setup AstroWind Template

This skill sets up a production-ready Astro 5.0 + Tailwind CSS template with perfect PageSpeed scores, dark mode, blog with RSS, and SEO optimization.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/astrowind-template.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Eng0AI/astrowind-template.git _temp_template
mv _temp_template/* _temp_template/.* . 2>/dev/null || true
rm -rf _temp_template
```

### 2. Remove Git History (Optional)

```bash
rm -rf .git
git init
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Verify Setup

```bash
npm run build
```

## Tech Stack

- **Framework**: Astro 5.0
- **Styling**: Tailwind CSS
- **Features**: Dark mode, RSS, SEO
- **Package Manager**: npm

## Next Steps

After setup, you can:
1. Customize content in `src/content/`
2. Run `npm run dev` to start development server (localhost:4321)
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
