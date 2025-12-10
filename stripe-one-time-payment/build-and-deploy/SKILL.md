---
name: build-and-deploy
description: Build and deploy this Stripe One-Time Payment application. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy Stripe One-Time Payment

> **CRITICAL: For Vercel, use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**

## Tech Stack

- **Backend**: Express.js
- **Payments**: Stripe Checkout
- **Language**: JavaScript
- **Package Manager**: npm
- **Port**: 4242

## Workflow

### 1. Install Dependencies

```bash
npm install
```

### 2. Verify Environment Variables

Ensure these are set in your environment or `.env` file:
- `STRIPE_SECRET_KEY` - Your Stripe secret key
- `STRIPE_PUBLISHABLE_KEY` - Your Stripe publishable key
- `PRICE` - Price ID from Stripe Dashboard
- `DOMAIN` - Your production domain (e.g., https://your-app.vercel.app)

### 3. Deploy

**Vercel (Recommended):**

```bash
vercel pull --yes -t $VERCEL_TOKEN
vercel build --prod -t $VERCEL_TOKEN
vercel deploy --prebuilt --prod --yes -t $VERCEL_TOKEN
```

Set environment variables in Vercel:
```bash
vercel env add STRIPE_SECRET_KEY production
vercel env add STRIPE_PUBLISHABLE_KEY production
vercel env add PRICE production
vercel env add DOMAIN production
```

**Netlify:**

For Netlify, you'll need to convert to Netlify Functions. Create `netlify/functions/api.js`:

```bash
netlify deploy --prod
```

## Going Live Checklist

1. **Switch API Keys**: Replace test keys (sk_test_/pk_test_) with live keys (sk_live_/pk_live_)
2. **Create Live Products**: Create products in Stripe Dashboard Live mode
3. **Complete KYC**: Finish Stripe account verification
4. **Update DOMAIN**: Set to your production URL
5. **Test Live Payment**: Make a small real payment to verify

## Environment Variables for Production

| Variable | Description | Example |
|----------|-------------|---------|
| `STRIPE_SECRET_KEY` | Live secret key | sk_live_xxx |
| `STRIPE_PUBLISHABLE_KEY` | Live publishable key | pk_live_xxx |
| `PRICE` | Live price ID | price_xxx |
| `DOMAIN` | Production URL | https://your-app.vercel.app |
| `PORT` | Server port (optional) | 4242 |

## Development

```bash
npm start
```

Opens at http://localhost:4242

## Notes

- Test mode uses cards like 4242 4242 4242 4242
- No webhook configuration required
- Payment verification via Checkout Session status polling
- Supports quantity selection (1-10 items)
