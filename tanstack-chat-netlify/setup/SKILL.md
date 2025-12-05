---
name: setup
description: Set up the TanStack Chat template in the current directory. Use when initializing a new project from this template.
---

# Setup TanStack Chat Template

This skill sets up a modern chat application with TanStack Router and Claude AI.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/netlify-templates/tanstack-template.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/netlify-templates/tanstack-template.git _temp_template
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

- **Framework**: React
- **Router**: TanStack Router
- **AI**: Claude AI integration
- **Package Manager**: npm
