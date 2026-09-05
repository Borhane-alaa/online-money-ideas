---
title: SaaS boilerplate flip
slug: saas-boilerplate-flip
status: back-burner
added: 2026-09-05
effort: 2
skill: 3
ceiling: 2
risk: 1
verdict: Passive-ish income ceiling ~$1k–$3k/mo. Real value is leverage — every future SaaS ships faster.
tags: [info-products, saas]
---

## Premise

Build a polished "indie hacker SaaS starter" (Next.js + auth + Stripe +
emails + dashboard + Postgres + a few example pages). Sell for $99–$299 on
Gumroad. Optional subscription for updates.

Examples: `marc-lou/ship-fast` ($199, $20k+ in early sales), `saas-starter`,
`next-saas-stripe-starter` from Vercel itself.

## How coding automates it

- One-time build, recurring sales. Delivery is automatic via license keys.
- Update subscribers get GitHub access.

## Evidence / Numbers

- Marc Lou's ShipFast: $20k+ in first 90 days (self-disclosed on X).
- Indie launches in this category routinely net $5k–$50k in year 1, decay
  sharply after the framework version goes stale.

## Cold-start plan

1. Take one of your own side projects and strip it to a clean starter.
2. Make a 10-minute demo video and a one-page README.
3. Launch on PH + IndieHackers + your own list.
4. Add a paid updates tier ($99 once / $39/yr for updates).

## Risks & gotchas

- **Maintenance** of the starter is real — security advisories in
  dependencies have to be backported.
- **Competition is brutal**: there are dozens of "Next.js SaaS starter"
  repos on GitHub. The premium is in polish + docs + support, not features.
- **Ceiling** is real and decays as frameworks ship their own
  starter ("create-next-app --example" already exists).

## Verdict

Back-burner. Worth doing only if (a) you'll reuse the starter on your own
projects anyway, or (b) you have audience. Otherwise the ceiling doesn't
justify the maintenance tax.