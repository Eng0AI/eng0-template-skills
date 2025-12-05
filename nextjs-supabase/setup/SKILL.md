---
name: setup
description: Set up the Next.js + Supabase template in the current directory. Use when initializing a new project from this template.
---

# Setup Next.js + Supabase Template

This skill sets up a full-stack application with Supabase backend.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+
- Supabase project

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/nextjs-supabase-template.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Eng0AI/nextjs-supabase-template.git _temp_template
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

Configure Supabase credentials in `.env.local`

### 5. Verify Setup

```bash
npm run build
```

## Tech Stack

- **Framework**: Next.js
- **React**: React
- **Database**: Supabase
- **Package Manager**: npm
