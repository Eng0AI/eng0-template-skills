---
name: setup
description: Set up the Developer Portfolio Pro template in the current directory. Use when initializing a new project from this template.
---

# Setup Developer Portfolio Pro Template

This skill sets up a modern, responsive portfolio with Next.js, Lottie animations, contact form with Email/Telegram, and dev.to blog integration.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- pnpm installed
- Node.js 18+

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/developer-portfolio-template.git .
```

If the directory is not empty:

```bash
git clone --depth 1 https://github.com/Eng0AI/developer-portfolio-template.git _temp_template
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

- **Framework**: Next.js 16
- **React**: React 19
- **Styling**: Tailwind CSS 4
- **Animation**: Lottie
- **Package Manager**: pnpm

## Customization

Edit content in `utils/data/`:
- `personal-data.js` - Name, bio, social links
- `experience.js` - Work history
- `projects-data.js` - Portfolio projects
- `skills.js` - Technical skills
- `educations.js` - Education background

## Next Steps

After setup, you can:
1. Customize your portfolio data
2. Run `pnpm dev` to start development server
3. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
