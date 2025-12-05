---
name: setup
description: Set up the AI Chatbot template in the current directory. Use when initializing a new project from this template.
---

# Setup AI Chatbot Template

This skill sets up a full-featured, hackable AI chatbot with authentication, file storage, and multi-model support.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm installed
- Node.js 18+
- PostgreSQL database (Neon, Supabase, or Railway)

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/ai-chatbot-template.git .
```

If the directory is not empty, clone to a temp directory and move files:

```bash
git clone --depth 1 https://github.com/Eng0AI/ai-chatbot-template.git _temp_template
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

Copy `.env.example` to `.env` and configure:

```bash
cp .env.example .env
```

Required variables:
- `POSTGRES_URL` - PostgreSQL connection string
- `AUTH_SECRET` - Generate with `openssl rand -base64 32`
- `OPENAI_API_KEY` or `ANTHROPIC_API_KEY` - LLM provider key

### 5. Run Database Migrations

```bash
pnpm db:migrate
```

### 6. Verify Setup

```bash
pnpm build
```

## Tech Stack

- **Framework**: Next.js 15
- **React**: React 19
- **AI**: AI SDK, Vercel AI Gateway
- **Auth**: Auth.js
- **ORM**: Drizzle
- **Database**: PostgreSQL
- **Styling**: Tailwind CSS, shadcn/ui
- **Package Manager**: pnpm

## Next Steps

After setup, you can:
1. Configure your LLM provider in the dashboard
2. Run `pnpm dev` to start development server (localhost:3000)
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
