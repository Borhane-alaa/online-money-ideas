---
title: Privacy-first web analytics SaaS
slug: privacy-first-analytics
status: validate-next
added: 2026-09-05
effort: 4
skill: 4
ceiling: 4
risk: 2
verdict: Real ceiling — Plausible is at $millions ARR solo-founded. Cookie-banner-free is a regulatory gift that keeps giving.
tags: [saas, data-products]
---

## Premise

Build a privacy-friendly alternative to Google Analytics: no cookies,
no personal data, GDPR/CCPA-compliant by default. Sell as a hosted
subscription.

## How coding automates it

- Server-side log analytics (no JS-heavy client).
- A small dashboard + a 2-line script for the user's site.
- Stripe for billing.
- Marketing is mostly SEO + GDPR-driven inbound ("how to drop GA4").

## Evidence / Numbers

- **Plausible Analytics** (solo founder, ~$3M+ ARR 2024).
- **Pirsch Analytics** (marvinblum, HN 35567822): hit $2k MRR in 1.5y,
  $4k MRR today. Two founders.
- **Fathom Analytics** (~$3M+ ARR 2024).
- **Simple Analytics** (~$1M+ ARR).
- All four are indie, solo or 2-person teams. Real revenue.

## Cold-start plan

1. Build the MVP: server-side analytics + tiny JS shim + dashboard.
2. Price at $9/mo or $0.5/1k events, freemium up to a page-view cap.
3. SEO is the moat — every "Google Analytics alternative" search is your
   funnel.
4. Build a transparent changelog (Plausible famously publishes
   public dashboards).
5. Privacy regs in EU + state-level US laws keep feeding the funnel.

## Risks & gotchas

- **Big-player risk**: Cloudflare Web Analytics is free; that's eating
  the bottom of the market.
- **Server costs**: log analytics is cheaper than GA but still has real
  storage cost at scale.
- **Devil in data**: some customers want funnels, sessions, attribution
  — privacy analytics deliberately doesn't ship those. Educate or lose.
- **Differentiation**: 4 indie privacy-analytics products already exist;
  the wedge is niche (e.g. one specific industry, or one specific
  integration).

## Verdict

Validate next. Real, proven ceiling. But the lane is increasingly
crowded — pick a vertical wedge (e.g. "privacy analytics for SaaS" or
"for ecommerce") and own it. Solo-feasable but the floor is high.

## Sources

- HN thread 35567822 (Pirsch Analytics disclosure by founder).
- Plausible public revenue dashboard (publicly disclosed, verifiable).
- Fathom & Simple Analytics public MRR ranges.