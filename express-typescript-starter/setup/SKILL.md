---
name: setup
description: Set up the Express TypeScript Starter template in the current directory. Use when initializing a new project from this template.
---

# Setup Express TypeScript Starter Template

This skill sets up Express + TypeScript starter with Biome, Docker, and Vitest.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/edwinhern/express-typescript.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/edwinhern/express-typescript.git _temp_template
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

- **Framework**: Express.js
- **Language**: TypeScript
- **Linting**: Biome
- **Testing**: Vitest
- **Package Manager**: npm
