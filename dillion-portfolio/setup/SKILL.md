---
name: setup
description: Set up the Developer Portfolio template in the current directory. Use when initializing a new project from this template.
---

# Setup Developer Portfolio Template

This skill sets up a minimalist developer portfolio with blog, work experience timeline, and project showcase.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/portfolio-template.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Eng0AI/portfolio-template.git _temp_template
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

### 4. Verify Setup

```bash
pnpm build
```

## Tech Stack

- **Framework**: Next.js 14
- **React**: React
- **Animation**: Framer Motion
- **Styling**: Tailwind CSS, shadcn/ui
- **Package Manager**: pnpm

## Customization

Edit content in the `src/data/` directory:
- `resume.tsx` - Personal info, work experience, education, projects

## Next Steps

After setup, you can:
1. Customize your portfolio content
2. Run `pnpm dev` to start development server
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
