---
name: setup
description: Set up the TailAdmin Dashboard template in the current directory. Use when initializing a new project from this template.
---

# Setup TailAdmin Dashboard Template

This skill sets up a free Next.js admin dashboard with 30+ components, dark mode, ApexCharts, calendar, forms, and tables.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/tailadmin-nextjs-template.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Eng0AI/tailadmin-nextjs-template.git _temp_template
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
pnpm install
```

### 4. Verify Setup

```bash
pnpm build
```

## Tech Stack

- **Framework**: Next.js 16
- **React**: React 19
- **Styling**: Tailwind CSS 4
- **Charts**: ApexCharts
- **Package Manager**: pnpm

## Next Steps

After setup, you can:
1. Customize dashboard pages
2. Run `pnpm dev` to start development server (localhost:3000)
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
