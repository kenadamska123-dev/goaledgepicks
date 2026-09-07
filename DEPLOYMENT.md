# GoalEdge Picks production checklist

## Frontend
Deploy the `frontend/` directory to a static HTTPS host.
Set the Supabase URL/key and API base URL in:
`frontend/js/config.js`, `frontend/auth.html`, `frontend/dashboard.html`, `frontend/admin.html`, and `frontend/results-admin.html`.

For production, use the same config values consistently.

## Backend
Deploy `server/` to a Node-compatible HTTPS host.
Set all values in `.env.example` as server environment variables.

Never commit `.env` or Stripe/Supabase secret keys.

## Supabase
1. Run `supabase/schema.sql`.
2. Configure Email/Password authentication.
3. Configure the production Site URL and redirect URLs.
4. Configure custom SMTP for reliable production email.
5. Create your first user and promote that user to `admin` through a controlled server/admin process.

## Stripe
1. Create GoalEdge Pro as a recurring Price.
2. Set `STRIPE_PRO_PRICE_ID`.
3. Enable Customer Portal.
4. Register `/api/stripe/webhook`.
5. Subscribe to customer/subscription lifecycle events.
6. Test in Stripe test mode before switching to live mode.

## Domain
Point `goaledgepicks.com` DNS to the chosen frontend host and API subdomain/host as appropriate.
Enable HTTPS.
Do not claim the domain is registered or connected until the registrar and DNS configuration have actually been completed.

## Before launch
- Replace all placeholders.
- Set a real Pro price.
- Add legal/privacy/terms pages appropriate to your jurisdiction.
- Add real support contact information.
- Verify tax/VAT obligations for subscriptions.
- Test password reset and email delivery.
- Test Checkout success/cancel paths.
- Test webhook delivery and subscription cancellation.
- Test RLS with a normal user and admin user.
- Remove all sample/demo prediction data or clearly label it.
- Do not publish guaranteed-win, fixed-match, or certainty claims.
