---
name: setup
description: Set up the Chrome Extension Boilerplate template in the current directory. Use when initializing a new project from this template.
---

# Setup Chrome Extension Boilerplate Template

This skill sets up a Chrome Extension Boilerplate with React + Vite + TypeScript.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Jonghakseo/chrome-extension-boilerplate-react-vite.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Jonghakseo/chrome-extension-boilerplate-react-vite.git _temp_template
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

### 4. Build Extension

```bash
pnpm build
```

## Tech Stack

- **Framework**: React
- **Build Tool**: Vite
- **Language**: TypeScript
- **Package Manager**: pnpm

## Loading Extension

1. Build the extension
2. Open Chrome and go to `chrome://extensions/`
3. Enable "Developer mode"
4. Click "Load unpacked" and select the `dist` folder
