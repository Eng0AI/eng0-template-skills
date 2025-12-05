---
name: build-and-deploy
description: Build and deploy this Next.js 16 developer portfolio. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy Developer Portfolio

> **CRITICAL: For Vercel, use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**

## Tech Stack

- **Framework**: Next.js 16 with App Router
- **UI**: React 19 + Tailwind CSS 4
- **Package Manager**: npm (or pnpm)
- **Output**: `.next` directory
- **Port**: 3000

## Workflow

### 1. Install Dependencies

```bash
npm install
```

### 2. Build

```bash
npm run build
```

### 3. Deploy

**Vercel (Recommended):**

```bash
vercel pull --yes -t $VERCEL_TOKEN
vercel build --prod -t $VERCEL_TOKEN
vercel deploy --prebuilt --prod --yes -t $VERCEL_TOKEN
```

**Netlify:**

```bash
netlify deploy --prod
```

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `NEXT_PUBLIC_GTM` | No | Google Tag Manager ID |
| `NEXT_PUBLIC_APP_URL` | Yes | Your portfolio's public URL |
| `TELEGRAM_BOT_TOKEN` | No | Telegram bot token for contact form |
| `TELEGRAM_CHAT_ID` | No | Telegram chat ID |
| `GMAIL_PASSKEY` | No | Gmail app password |
| `EMAIL_ADDRESS` | No | Gmail address for contact form |

## Customization

Portfolio content is configured in `utils/data/`:

- `personal-data.js` - Name, bio, social links
- `experience.js` - Work history
- `projects-data.js` - Portfolio projects
- `skills.js` - Technical skills
- `educations.js` - Education background

## Notes

- Requires Node.js 18.17+ (Node.js 20+ recommended)
- Contact form requires Gmail or Telegram configuration
- Blog section auto-fetches from dev.to (set `devUsername` in personal-data.js)
