---
name: build-and-deploy
description: Build and deploy this AI Chatbot application. Use when building, deploying, setting up database, or preparing the project for production. Triggers on requests to build, deploy, setup database, or publish.
---

# Build and Deploy AI Chatbot

## Workflow

### 1. Setup Environment Variables

**Read `.env.example` to see all required variables:**

```bash
cat .env.example
```

**Create `.env` by reading values from current environment:**

For each variable in `.env.example`, read the value from the current environment and write to `.env`. Example approach:

```bash
# Read .env.example and create .env with values from current environment
while IFS= read -r line || [[ -n "$line" ]]; do
  # Skip comments and empty lines
  [[ "$line" =~ ^#.*$ || -z "$line" ]] && continue
  # Extract variable name (before = sign)
  var_name=$(echo "$line" | cut -d'=' -f1)
  # Get value from environment
  var_value="${!var_name}"
  # Write to .env
  echo "${var_name}=${var_value}" >> .env
done < .env.example
```

Or manually inspect `.env.example` and create `.env` with the required values from environment variables.

### 2. Install Dependencies

```bash
pnpm install
```

### 3. Run Database Migrations

```bash
pnpm db:migrate
```

### 4. Build

```bash
pnpm build
```

Or run build without migration (if already migrated):
```bash
next build
```

### 5. Deploy

**Vercel (Recommended):**

All vercel CLI commands require `-t <token>` or `--token <token>` for authentication.

```bash
# Pull project settings (also links project, creates .vercel/project.json)
vercel pull --yes -t $VERCEL_TOKEN

# Push env vars to Vercel (first time only)
# Must add to each environment separately
while IFS='=' read -r key value; do
  [[ "$key" =~ ^#.*$ || -z "$key" || -z "$value" ]] && continue
  for env in production preview development; do
    printf '%s' "$value" | vercel env add "$key" $env -t $VERCEL_TOKEN
  done
done < .env

# Build locally for production
vercel build --prod -t $VERCEL_TOKEN

# Deploy prebuilt
vercel deploy --prebuilt --prod --yes -t $VERCEL_TOKEN
```

**Netlify:**
```bash
# Import all env vars from .env (first time only)
netlify env:import .env

# Deploy
netlify deploy --prod
```

## Critical Notes

- **Database Required:** Must have PostgreSQL database set up before building
- **Migration Required:** Run `pnpm db:migrate` before first build
- **Auth Secret:** Generate a secure random secret for AUTH_SECRET
- **Environment Variables:** All values come from current environment - inspect `.env.example` for required variables
- **No Dev Server:** Never run `pnpm dev` in VM environment
