---
name: setup
description: Set up the Vite Vue template in the current directory. Use when initializing a new project from this template.
---

# Setup Vite Vue Template

This skill sets up a lightning-fast Vue 3.5 development environment with Vite 7 and TypeScript.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/vite-vue-template.git .
```

If the directory is not empty, clone to a temp directory and move files:

```bash
git clone --depth 1 https://github.com/Eng0AI/vite-vue-template.git _temp_template
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
npm install
```

### 4. Verify Setup

```bash
npm run build
```

## Tech Stack

- **Framework**: Vue 3.5
- **Build Tool**: Vite 7
- **Language**: TypeScript
- **Package Manager**: npm

## Next Steps

After setup, you can:
1. Run `npm run dev` to start development server (localhost:5173)
2. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
