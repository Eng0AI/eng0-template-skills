---
name: setup
description: Set up the Mantis React Admin template in the current directory. Use when initializing a new project from this template.
---

# Setup Mantis React Admin Template

This skill sets up a free React admin dashboard with Material UI v7, React 19, Vite 7, and MUI X Charts.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/mantis-react-admin-template.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Eng0AI/mantis-react-admin-template.git _temp_template
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

- **Framework**: React 19
- **Build Tool**: Vite 7
- **UI Library**: Material UI v7, MUI X Charts
- **Package Manager**: npm

## Next Steps

After setup, you can:
1. Customize dashboard components
2. Run `npm run dev` to start development server (localhost:5173)
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
