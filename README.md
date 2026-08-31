# Carpool India — Console

Ops/admin dashboard, Vite + React. Deployed on Vercel via `vercel.json`.

## Setup

```bash
cp .env.example .env   # fill in Supabase + backend service URLs
npm install
npm run dev
```

`shared/types` is a vendored copy of the backend's shared TypeScript contracts (linked via a `file:` dependency in `package.json`) — if the backend's types change, copy the updated files into `shared/types` here and rebuild:

```bash
cd shared/types && npx tsc -p tsconfig.json
```

## Env vars

Set these in Vercel (Project Settings → Environment Variables) — all read at build time by Vite:

```
VITE_SUPABASE_URL
VITE_SUPABASE_ANON_KEY
VITE_BOOKING_SERVICE_URL
VITE_SAFETY_SERVICE_URL
VITE_PAYMENT_SERVICE_URL
VITE_GOOGLE_MAPS_API_KEY   (optional)
```

## Deploy

Connect this repo in Vercel — `vercel.json` handles the build command, output directory, and the SPA rewrite needed for `react-router-dom`.
