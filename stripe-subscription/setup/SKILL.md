---
name: setup
description: Set up the Stripe Subscription template in the current directory. Use when initializing a new project from this template.
---

# Setup Stripe Subscription Template

This skill sets up a Stripe Checkout integration for recurring subscriptions. No webhook configuration required.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+
- Stripe account (test or live mode)

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/stripe-subscription.git .
```

If the directory is not empty, clone to a temp directory and move files:

```bash
git clone --depth 1 https://github.com/Eng0AI/stripe-subscription.git _temp_template
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
npm install
```

### 4. Setup Environment Variables

Create `.env` from the example:

```bash
cp .env.example .env
```

**Required variables:**
- `STRIPE_SECRET_KEY` - Your Stripe secret key (sk_test_xxx)
- `STRIPE_PUBLISHABLE_KEY` - Your Stripe publishable key (pk_test_xxx)

Get your API keys from: https://dashboard.stripe.com/apikeys

**Optional variables:**
- `BASIC_PRICE` - Price ID for Starter plan (price_xxx)
- `PRO_PRICE` - Price ID for Professional plan (price_xxx)

If price IDs are not set, default subscription plans will be auto-created on first start:
- Starter Plan: $12/month
- Professional Plan: $18/month

### 5. Start the Server

```bash
npm start
```

The server will:
1. Check for required environment variables
2. If price IDs are not set, automatically create subscription products and prices via Stripe API
3. Save the auto-generated price IDs to `.env` for persistence
4. Start listening on http://localhost:4242

**Expected output (first run without price IDs):**
```
Price IDs not fully configured. Creating default products and prices via Stripe API...
Created Basic product: prod_xxx
Created Pro product: prod_xxx
Created Basic price: price_xxx
Created Pro price: price_xxx
Saved price IDs to .env file

✓ Subscription plans ready!
  Starter Plan: $12/month (price_xxx)
  Professional Plan: $18/month (price_xxx)

Server running at http://localhost:4242
Using Stripe API in TEST mode
```

## Tech Stack

- **Backend**: Express.js
- **Payments**: Stripe Checkout + Customer Portal
- **Language**: JavaScript
- **Package Manager**: npm
- **Port**: 4242

## Testing

Use test card numbers:
- **Success**: 4242 4242 4242 4242
- **Decline**: 4000 0000 0000 0002

Any future expiry date and any 3-digit CVC will work.

## Features

- Two-tier pricing (Starter & Professional)
- Stripe Checkout for secure subscription signup
- Customer Portal for subscription management
- No webhook required for basic functionality

## Customizing Plans

To use your own subscription plans instead of the auto-created ones:
1. Go to [Stripe Dashboard > Products](https://dashboard.stripe.com/products)
2. Create your subscription products with recurring prices
3. Copy the Price IDs (starts with `price_`)
4. Add `BASIC_PRICE=price_xxx` and `PRO_PRICE=price_xxx` to your `.env` file
5. Restart the server

## Next Steps

After setup, you can:
1. Customize the pricing page in `client/html/index.html`
2. Modify subscription tiers in Stripe Dashboard
3. Adjust styling in `client/html/css/global.css`
4. Run `npm start` to start development server
5. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
