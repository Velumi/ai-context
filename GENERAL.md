# Velumi — AI Context Brief

Condensed context for AI agents working across Velumi repos.
For full detail, see the `velumi/playbook` repo (private).

---

## What Is Velumi

**Managed PaaS for Next.js and static sites** — European Vercel alternative.
Built by **Templ** (Wootemple AB), a Swedish managed WordPress host for web agencies.

| Field | Detail |
|---|---|
| Legal entity | Velumisphere AB (org. nr 556999-0699), Sweden |
| Parent company | Wootemple AB (Templ) |

---

## Positioning

**Mission:** Modern web infrastructure, built and hosted in Europe.
**Brand pillars:** Calm, Approachable, Trustworthy.

**Key differentiators vs Vercel:**

1. **EU data residency by default** — all data/compute in EU (Sweden). GDPR-ready. No add-on.
2. **Predictable pricing** — flat-rate per-project tiers. No seat fees. Bandwidth only usage metric.
3. **Agency-friendly** — per-project pricing lets agencies resell with markup.
4. **Vibecoder-friendly** — dead-simple deploy for Lovable/Bolt/v0 users.

**Never frame Velumi as "cheaper Vercel."** The story is *predictable*, not *cheap*.
**Never name Vercel negatively in public-facing copy.** Position against the problem, not the competitor.

> Ref: `velumi/playbook` → `03-positioning-mission.md`

---

## ICPs (brief)

1. **Web agencies** (priority #1) — 2–20 people, WordPress + growing Next.js. Switch trigger: surprise Vercel bills, EU compliance.
2. **Freelancers** (#2) — solo devs, price-sensitive. Want cheap-enough-to-forget hosting.
3. **Vibecoders** (#3, highest growth) — build with Lovable/Bolt/v0, need "real" hosting with custom domain.

**Cross-segment truth:** All want deploy-and-forget. Surprise bills = dealbreaker. EU residency increasingly non-negotiable.

> Ref: `velumi/playbook` → `02-icp-jtbd.md`

---

## Pricing Model

**One plan = one project.** No seat fees. Unlimited team members.
**Bandwidth** is the only usage-based metric.

Five tiers: Dev (free, 10 GB BW) → Launch (€9) → Grow (€49) → Scale (€199) → Enterprise (custom).
All prices ex. VAT. Annual = 2 months free.

Dev tier: no custom domains, no commercial use, noindex, max 10 free projects.

> Ref: `velumi/playbook` → `04-plans-pricing.md`

---

## Billing Model

Hybrid: base plan upfront, bandwidth overage charged end of billing period.
One Stripe subscription per account. Each paid site = 2 subscription items (base + metered overage).

Key mechanics: anniversary billing, no bandwidth rollover, prorated upgrades/downgrades.

> Ref: `velumi/playbook` → `04c-how-billing-works.md`

---

## Competitor Quick Reference

| Platform | Starting Price | Main Weakness for Our ICPs |
|---|---|---|
| Vercel | $20/seat/mo | 9 usage meters, surprise bills, US-centric |
| Netlify | $19/seat/mo | BW overages, limited Next.js |
| Railway | $5/mo + usage | Usage-based spikes, limited EU regions |
| Render | $7/mo | Cold starts, limited regions, slow builds |
| Fly.io | ~$5/mo + usage | Steep learning curve, complex pricing |
| Cloudflare Pages | Free–$20/mo | Partial Next.js, no Node.js runtime |

**Empty quadrant:** No EU-native managed PaaS with Vercel-like DX exists.

> Ref: `velumi/playbook` → `01-market-research.md`

---

## GTM

- **North star:** 100 paying customers in 6 months
- **Phase 1:** Convert Templ customers, build waitlist
- **Phase 2:** SEO, PLG activation, community, partnerships (Lovable/Bolt priority)
- **Templ relationship is strategic** — existing agency customers are #1 early adopter channel

> Ref: `velumi/playbook` → `05-marketing-gtm.md`
