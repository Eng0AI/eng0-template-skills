---
name: build-and-deploy
description: Build and deploy this Evidence framework project. Use when building, deploying, or setting up the happiness dashboard project. Triggers on requests to build, deploy, publish, or prepare the project for production.
---

# Build and Deploy Happiness Dashboard

## Environment

All required environment variables are pre-configured in CCVM and available directly:
- `VERCEL_TOKEN` - For Vercel CLI authentication
- `NETLIFY_AUTH_TOKEN` - For Netlify CLI authentication

No `.env` file setup required for Evidence projects.

## Workflow

### 1. Install Dependencies

```bash
pnpm install
```

**Requirements:**
- Node.js 18+ (pnpm with `shamefully-hoist=true` and duckdb override resolves compatibility)
- pnpm 8+

### 2. Process Data Sources

```bash
pnpm run sources
```

Processes CSV files from `sources/happiness_score/`:
- `hs2024.csv` - Current year happiness data
- `hsArchive.csv` - Historical happiness data

### 3. Build

```bash
pnpm run build
```

Generates static site in `build/` directory.

### 4. Deploy

**Vercel:**

All vercel CLI commands require `-t <token>` or `--token <token>` for authentication.

```bash
# Pull project settings (also links project, creates .vercel/project.json)
vercel pull --yes -t $VERCEL_TOKEN

# Build locally for production
vercel build --prod -t $VERCEL_TOKEN

# Deploy prebuilt
vercel deploy --prebuilt --prod --yes -t $VERCEL_TOKEN
```

**Important:** Deploy from project root, not `build/` directory.

**Netlify:**
```bash
# First deployment
netlify deploy --prod --dir=build --create-site

# Subsequent deployments
netlify deploy --prod --dir=build
```

## Critical Notes

- **Package Manager:** Use pnpm (not npm). The `.npmrc` has `shamefully-hoist=true` for Evidence compatibility
- **Node Version:** Node.js 18+ works with pnpm overrides for duckdb
- **Build Locally:** Always build locally before deploying (Vercel/Netlify build can timeout due to DuckDB compilation taking 40+ minutes)
- **Deploy Location:** Run deploy command from project root, not build directory
- **No Database:** Uses CSV files, no database setup needed
- **No Dev Server:** Never run `pnpm run dev` in VM environment
