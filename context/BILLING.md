# Billing — AI Context

Cross-project billing ownership rules. For deep technical spec, see `billing-service/docs/billing-plan.md`.

---

## Ownership

| Component | Owns | Stripe SDK? |
|---|---|---|
| `@velumi/billing` | Pure data: types, plan defs, prices, Price ID lookups, formatters, org field schemas | No |
| `billing-service` | ALL Stripe operations: checkout, webhooks, subscriptions, invoices, dunning | Yes (sole owner) |
| `dashboard` | Billing UI + proxy to billing-service. Embeds checkout via `@stripe/stripe-js` | Client-side only |
| `login` | Stores Stripe IDs + mirrored billing fields on org. Written by billing-service only | No |
| `website` | Display-only pricing from `@velumi/billing`. WordPress plans are separate/hardcoded | No |

## Rules

- **Stripe SDK server-side: billing-service only.** Never add `stripe` package elsewhere.
- **Org billing fields are webhook-written.** Never write them directly — billing-service mirrors from Stripe via login API.
- **Plan data: import `@velumi/billing`.** Never hardcode plan names, prices, or limits. Exception: website WordPress plans — intentionally separate product line.
- **Dashboard never calls Stripe directly.** All Stripe ops proxy through billing-service API.
- **Currency locks at first checkout.** Never allow currency changes after first paid site.

## Paid Site Flow

Dashboard pre-creates pending site → proxies to billing-service → Stripe Checkout → `checkout.session.completed` webhook → billing-service calls dashboard to activate site. Dev (free) sites skip billing entirely.

## Data Model

- Stripe Customer = Velumi Organization (1:1)
- One subscription per account. Each paid site = 2 subscription items (base plan + metered bandwidth overage)
- Mirror fields on org (billingEmail, subscriptionStatus, etc.) = read-only webhook copies, never source of truth

> Ref: `billing-service/docs/billing-plan.md`, `velumi/playbook` → `04c-how-billing-works.md`
