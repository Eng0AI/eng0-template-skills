---
name: setup
description: Set up the Next.js Blog template in the current directory. Use when initializing a new project from this template.
---

# Setup Next.js Blog Template

This skill sets up a customizable blog with visual editing and Tailwind CSS.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/netlify-templates/nextjs-blog-theme.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/netlify-templates/nextjs-blog-theme.git _temp_template
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

- **Framework**: Next.js
- **React**: React
- **Styling**: Tailwind CSS
- **Package Manager**: npm

## Next Steps

After setup, you can:
1. Customize blog content
2. Run `npm run dev` to start development server
3. Deploy to Netlify
