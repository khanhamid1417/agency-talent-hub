## Agency Talent Hub (MVP scaffold)

### What you get
- **Frontend**: Next.js (App Router) + Tailwind UI pages for Achievements, Contracts, Apply, Boost, Feedback, Dashboard
- **Database**: Supabase SQL schema + RLS in `supabase/migrations/001_initial_schema.sql`
- **Payouts**: Cashfree Payouts (authorize → add beneficiary → transfer) server routes

### Prerequisites
- Node.js 18+ (recommended 20+)
- A Supabase project
- Cashfree Payouts enabled (sandbox or production)

### 1) Configure Supabase
1. Create a Supabase project
2. In Supabase SQL Editor, run:
   - `supabase/migrations/001_initial_schema.sql`
3. In **Storage**, create buckets:
   - `cvs` (private)
   - `videos` (private)

### 2) Configure env
Copy `.env.example` to `.env.local`:

```bash
cp .env.example .env.local
```

Fill:
- `NEXT_PUBLIC_SUPABASE_URL`
- `NEXT_PUBLIC_SUPABASE_ANON_KEY`
- `CASHFREE_PAYOUT_*`
- `INTERNAL_API_SECRET`

### 3) Install and run

```bash
npm install
npm run dev
```

Open `http://localhost:3000`.

### 4) Cashfree payout endpoints (server)
These are protected with `x-admin-secret: INTERNAL_API_SECRET`.

- `POST /api/payouts/beneficiary`
- `POST /api/payouts/transfer`

### Notes / next steps
- Add Supabase Auth UI (login, agency creation, contract posting).
- Connect Apply page to Supabase Storage uploads + insert into `applications`.
- Add Cashfree **payment collection** (Orders/PG) for Boost + Feedback purchases (separate from payouts).

