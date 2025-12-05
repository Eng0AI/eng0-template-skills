---
name: setup
description: Set up the Gatsby E-commerce template in the current directory. Use when initializing a new project from this template.
---

# Setup Gatsby E-commerce Template

This skill sets up an e-commerce starter with styled components.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/netlify-templates/gatsby-ecommerce-theme.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/netlify-templates/gatsby-ecommerce-theme.git _temp_template
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

- **Framework**: Gatsby
- **React**: React
- **Styling**: Styled Components
- **Package Manager**: npm
