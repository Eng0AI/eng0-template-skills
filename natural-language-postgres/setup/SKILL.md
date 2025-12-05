---
name: setup
description: Set up the Chat App On Your Data template in the current directory. Use when initializing a new project from this template.
---

# Setup Natural Language Postgres Template

This skill sets up a demo app that lets you ask questions in plain English and get answers from your database.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm installed
- Node.js 18+
- PostgreSQL database

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/natural-language-postgres.git .
```

If the directory is not empty, clone to a temp directory and move files:

```bash
git clone --depth 1 https://github.com/Eng0AI/natural-language-postgres.git _temp_template
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
pnpm install
```

### 4. Setup Environment Variables

Create `.env` with required variables:
- `POSTGRES_URL` - PostgreSQL connection string
- `OPENAI_API_KEY` or other LLM provider key

### 5. Verify Setup

```bash
pnpm build
```

## Tech Stack

- **Framework**: Next.js
- **AI**: AI SDK
- **Database**: PostgreSQL
- **Package Manager**: pnpm

## Next Steps

After setup, you can:
1. Connect your PostgreSQL database
2. Run `pnpm dev` to start development server
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
