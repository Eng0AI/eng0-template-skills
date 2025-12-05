---
name: setup
description: Set up the LangChain Agent template in the current directory. Use when initializing a new project from this template.
---

# Setup LangChain Agent Template

This skill sets up an AI agent with tools (search engine and calculator) powered by LangGraph and the Vercel AI SDK.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm installed
- Node.js 18+
- PostgreSQL database

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/langchain-agent.git .
```

If the directory is not empty, clone to a temp directory and move files:

```bash
git clone --depth 1 https://github.com/Eng0AI/langchain-agent.git _temp_template
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
- `OPENAI_API_KEY` - OpenAI API key for the agent

### 5. Verify Setup

```bash
pnpm build
```

## Tech Stack

- **Framework**: Next.js
- **AI**: LangChain.js, LangGraph, AI SDK
- **Database**: PostgreSQL
- **Package Manager**: pnpm

## Next Steps

After setup, you can:
1. Configure additional tools for the agent
2. Run `pnpm dev` to start development server
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
