---
name: setup
description: Set up the Stripe One-Time Payment template in the current directory. Use when initializing a new project from this template.
---

# Setup Stripe One-Time Payment Template

This skill sets up a Stripe Checkout integration for accepting one-time payments. No webhook configuration required.

## Prerequisites

- Empty or nearly empty directory
- Git installed
- npm installed
- Node.js 18+
- Stripe account (test or live mode)

## Workflow

### 1. Clone the Template

```bash
git clone --depth 1 https://github.com/Eng0AI/stripe-one-time-payment.git .
```

If the directory is not empty, clone to a temp directory and move files:

```bash
git clone --depth 1 https://github.com/Eng0AI/stripe-one-time-payment.git _temp_template
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
- `PRICE` - Price ID from Stripe Dashboard (price_xxx). If not set, a default product ($20) will be auto-created on first start.

### 5. Start the Server

```bash
npm start
```

The server will:
1. Check for required environment variables
2. If `PRICE` is not set, automatically create a sample product and price via Stripe API
3. Save the auto-generated price ID to `.env` for persistence
4. Start listening on http://localhost:4242

**Expected output (first run without PRICE):**
```
No PRICE configured. Creating default product and price via Stripe API...
Created product: prod_xxx
Created price: price_xxx
Saved PRICE to .env file

✓ Product and price ready!
  Product: Sample Product
  Price: $20 USD
  Price ID: price_xxx

Server running at http://localhost:4242
Using Stripe API in TEST mode
```

## Tech Stack

- **Backend**: Express.js
- **Payments**: Stripe Checkout
- **Language**: JavaScript
- **Package Manager**: npm
- **Port**: 4242

## Testing

Use test card numbers:
- **Success**: 4242 4242 4242 4242
- **Decline**: 4000 0000 0000 0002

Any future expiry date and any 3-digit CVC will work.

## Customizing Products

To use your own products instead of the auto-created one:
1. Go to [Stripe Dashboard > Products](https://dashboard.stripe.com/products)
2. Click "Add product"
3. Set name, description, and one-time price
4. Copy the Price ID (starts with `price_`)
5. Add `PRICE=price_xxx` to your `.env` file
6. Restart the server

## Next Steps

After setup, you can:
1. Customize the product page in `client/html/index.html`
2. Modify pricing and products in Stripe Dashboard
3. Run `npm start` to start development server
4. Use the `build-and-deploy` skill to deploy to Vercel or Netlify
