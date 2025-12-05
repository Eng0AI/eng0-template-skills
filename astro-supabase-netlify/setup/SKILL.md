---
name: setup
description: Set up the Astro + Supabase template in the current directory. Use when initializing a new project from this template.
---

# Setup Astro + Supabase Template

This skill sets up Astro with Supabase integration.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+
- Supabase project

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/netlify-templates/astro-supabase-starter.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/netlify-templates/astro-supabase-starter.git _temp_template
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

### 4. Setup Environment

Configure Supabase credentials in `.env`

### 5. Verify Setup

```bash
npm run build
```

## Tech Stack

- **Framework**: Astro
- **Database**: Supabase
- **Package Manager**: npm
