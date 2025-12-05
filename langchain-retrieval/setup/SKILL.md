---
name: setup
description: Set up the LangChain Retrieval template in the current directory. Use when initializing a new project from this template.
---

# Setup LangChain Retrieval Template

This skill sets up a document Q&A with RAG (Retrieval Augmented Generation) using Supabase vector store.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm installed
- Node.js 18+
- Supabase project with pgvector extension

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/langchain-retrieval.git .
```

If the directory is not empty, clone to a temp directory and move files:

```bash
git clone --depth 1 https://github.com/Eng0AI/langchain-retrieval.git _temp_template
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
- `SUPABASE_URL` - Supabase project URL
- `SUPABASE_PRIVATE_KEY` - Supabase service role key
- `OPENAI_API_KEY` - For embeddings and LLM
- `SUPABASE_DB_URL` - Direct PostgreSQL connection URL

### 5. Setup Vector Store

Initialize pgvector extension and create documents table in Supabase.

### 6. Verify Setup

```bash
pnpm build
```

## Tech Stack

- **Framework**: Next.js
- **AI**: LangChain.js, AI SDK
- **Vector Store**: Supabase pgvector
- **Package Manager**: pnpm

## Next Steps

After setup, you can:
1. Upload documents to the vector store
2. Run `pnpm dev` to start development server
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
