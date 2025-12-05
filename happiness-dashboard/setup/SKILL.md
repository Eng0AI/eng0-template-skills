---
name: setup
description: Set up the Happiness Dashboard template in the current directory. Use when initializing a new project from this template.
---

# Setup Happiness Dashboard Template

This skill sets up an interactive data dashboard using Evidence framework - write SQL queries in markdown to create visualizations.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/happiness-dashboard-template.git .
```

If the directory is not empty, clone to a temp directory and move files:

```bash
git clone --depth 1 https://github.com/Eng0AI/happiness-dashboard-template.git _temp_template
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

### 4. Process Data Sources

```bash
pnpm run sources
```

### 5. Verify Setup

```bash
pnpm run build
```

## Tech Stack

- **Framework**: Evidence
- **Database**: DuckDB (embedded)
- **Frontend**: Svelte
- **Package Manager**: pnpm

## Data Sources

CSV files in `sources/happiness_score/`:
- `hs2024.csv` - Current year happiness data
- `hsArchive.csv` - Historical happiness data

## Next Steps

After setup, you can:
1. Add your own data sources to `sources/` directory
2. Create new pages in `pages/` with SQL queries in markdown
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
