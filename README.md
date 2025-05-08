# Baker Order Tracker App

A Kawaii-themed responsive web app for bakers to manage cake orders, subscriptions, and supplies.

## 🔧 Stack
- Next.js (React)
- Firebase (Auth, Firestore, Storage)
- Stripe (Payments)
- Tailwind CSS + ShadCN UI

## 🚀 Deploy Instructions

### 1. Firebase Setup
- Enable Firebase Auth (Email/Password)
- Enable Firestore & Storage
- Create a service account key (Admin SDK) and copy it into `.env` as `FIREBASE_ADMIN_KEY`

### 2. Stripe Setup
- Create products/plans
- Add pricing IDs into `priceMap` in `/api/checkout.ts`
- Get webhook secret using:
```bash
stripe listen --forward-to localhost:3000/api/webhook
```

### 3. Environment Variables
Add these to `.env.local`:
```
NEXT_PUBLIC_APP_URL=https://yourapp.vercel.app
NEXT_PUBLIC_FIREBASE_API_KEY=...
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=...
NEXT_PUBLIC_FIREBASE_PROJECT_ID=...
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=...
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=...
NEXT_PUBLIC_FIREBASE_APP_ID=...
STRIPE_SECRET_KEY=sk_test_...
STRIPE_WEBHOOK_SECRET=whsec_...
FIREBASE_ADMIN_KEY={"type":"service_account", ...}
```

### 4. Vercel Deployment
- Push repo to GitHub
- Connect GitHub repo in Vercel
- Add above env variables