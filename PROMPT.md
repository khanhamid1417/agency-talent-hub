## Master prompt (copy/paste)

You are a senior product engineer and architect. Build an **Agency Talent Hub** web app where:

### Core users
- **Agency owners** (create agency, post contracts, sell paid feedback sessions, manage payouts)
- **Agency employees** (linked to an agency; can post achievements)
- **Independent talent** (not linked to an agency; can apply to contracts and buy Boost)

### Core features
1. **Achievements feed**
   - Agency owners + employees post achievements (title, description, media links)
   - Public feed + agency filter
2. **Contract-based hiring**
   - Agencies post contracts (open/closed)
   - Applicants submit in **video** format or **CV** format or **both**
   - Upload CV/video to storage; store application row in database
3. **Boost phase (paid plan)**
   - Indie talent can buy “Boost” plans for visibility
   - Show line items including **GST**
4. **Paid guidance / prescribed feedback**
   - Agency owners offer feedback sessions for a price
   - Total should include **platform fee + GST** (GST applied on platform fee portion)
   - After completion, pay out to the talent via **Cashfree Payouts**

### Payments
- Use **Cashfree**:
  - **Payment collection** (Orders/PG) for Boost + Feedback purchases
  - **Payouts** for transferring money to talent after sessions complete
- Include platform fee and GST in the pricing breakdown and persisted receipts

### Tech constraints
- Frontend: Next.js (App Router) + Tailwind
- Database/Auth/Storage: Supabase
- Security: RLS policies, server-only secrets, webhook verification, idempotency keys for payment & payouts

### Deliverables
- Full working codebase: frontend, API routes, DB schema/migrations, env template, README run steps
- Supabase SQL schema with RLS for:
  - profiles, agencies, members, achievements, contracts, applications
  - boost plans & subscriptions
  - feedback sessions, reviews, payouts ledger
- Cashfree integration code:
  - Create/verify payment (collection) for Boost + Feedback
  - Add beneficiary + transfer payout for feedback completion

### Output requirements
- Provide complete file tree and code. Keep code production-grade: validation, error handling, and clear structure.

