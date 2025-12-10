---
name: build-and-deploy
description: Build and deploy this Stripe Subscription application. Use when building, deploying, or preparing the project for production.
---

# Build and Deploy Stripe Subscription

> **CRITICAL: For Vercel, use `vercel build --prod` then `vercel deploy --prebuilt --prod`.**

## Tech Stack

- **Backend**: Express.js
- **Payments**: Stripe Checkout + Customer Portal
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
- `BASIC_PRICE` - Price ID for Starter plan
- `PRO_PRICE` - Price ID for Professional plan
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
vercel env add BASIC_PRICE production
vercel env add PRO_PRICE production
vercel env add DOMAIN production
```

**Netlify:**

For Netlify, you'll need to convert to Netlify Functions:

```bash
netlify deploy --prod
```

## Going Live Checklist

1. **Switch API Keys**: Replace test keys (sk_test_/pk_test_) with live keys (sk_live_/pk_live_)
2. **Create Live Products**: Create subscription products in Stripe Dashboard Live mode
3. **Complete KYC**: Finish Stripe account verification
4. **Configure Customer Portal**: Set up portal in [Stripe Dashboard > Settings > Billing > Customer Portal](https://dashboard.stripe.com/settings/billing/portal)
5. **Update DOMAIN**: Set to your production URL
6. **Test Live Subscription**: Make a small real subscription to verify

## Environment Variables for Production

| Variable | Description | Example |
|----------|-------------|---------|
| `STRIPE_SECRET_KEY` | Live secret key | sk_live_xxx |
| `STRIPE_PUBLISHABLE_KEY` | Live publishable key | pk_live_xxx |
| `BASIC_PRICE` | Live Starter plan price ID | price_xxx |
| `PRO_PRICE` | Live Professional plan price ID | price_xxx |
| `DOMAIN` | Production URL | https://your-app.vercel.app |
| `PORT` | Server port (optional) | 4242 |

## Customer Portal Configuration

Before going live, configure the Customer Portal:

1. Go to [Stripe Dashboard > Settings > Billing > Customer Portal](https://dashboard.stripe.com/settings/billing/portal)
2. Enable features:
   - Update payment method
   - Cancel subscription
   - Switch plans (if applicable)
3. Save configuration

## Development

```bash
npm start
```

Opens at http://localhost:4242

## Notes

- Test mode uses cards like 4242 4242 4242 4242
- No webhook configuration required
- Subscription verification via Checkout Session status
- Customer Portal for self-service subscription management
- Supports plan switching and cancellation
