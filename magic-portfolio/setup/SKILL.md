---
name: setup
description: Set up the Magic Portfolio template in the current directory. Use when initializing a new project from this template.
---

# Setup Magic Portfolio Template

This skill sets up a simple, clean portfolio template with MDX-based blog and projects, automatic SEO, gallery, and endless theming options.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/magic-portfolio-template.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Eng0AI/magic-portfolio-template.git _temp_template
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

### 4. Verify Setup

```bash
npm run build
```

## Tech Stack

- **Framework**: Next.js 16
- **React**: React 19
- **Content**: MDX
- **UI**: Once UI
- **Package Manager**: npm

## Customization

Edit content:
- `src/app/resources/content.js` - Personal info, work, projects
- `src/app/blog/posts/` - Blog posts in MDX
- `src/app/work/projects/` - Project case studies

## Next Steps

After setup, you can:
1. Customize your portfolio content
2. Run `npm run dev` to start development server
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
