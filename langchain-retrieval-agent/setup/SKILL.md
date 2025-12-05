---
name: setup
description: Set up the LangChain Retrieval Agent template in the current directory. Use when initializing a new project from this template.
---

# Setup LangChain Retrieval Agent Template

This skill sets up an AI agent with retrieval tool for document Q&A using RAG, powered by LangGraph.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm installed
- Node.js 18+
- Supabase project with pgvector extension

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/langchain-retrieval-agent.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Eng0AI/langchain-retrieval-agent.git _temp_template
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

### 4. Setup Environment Variables

- `SUPABASE_URL` - Supabase project URL
- `SUPABASE_PRIVATE_KEY` - Supabase service role key
- `OPENAI_API_KEY` - For embeddings and LLM

### 5. Verify Setup

```bash
pnpm build
```

## Tech Stack

- **Framework**: Next.js
- **AI**: LangChain.js, LangGraph, AI SDK
- **Vector Store**: Supabase pgvector
- **Package Manager**: pnpm
