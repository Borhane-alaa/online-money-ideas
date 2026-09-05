---
title: Micro-SaaS for one ignored vertical
slug: micro-saas-niche-vertical
status: validate-next
added: 2026-09-05
effort: 4
skill: 4
ceiling: 4
risk: 2
verdict: Best ROI per line of code if you pick the right vertical — but vertical picking is everything.
tags: [saas]
---

## Premise

Build the smallest possible subscription web app that solves one painful,
recurring problem for one specific type of user (e.g. property managers, indie
podcast editors, dental clinics, Etsy shop owners). Charge $19–$99/mo.

The "micro-SaaS" thesis (popularized by Tyler Tringas / MicroConf, Marc
Lou / ShipFast, and ~300 other indie hackers): a niche big enough to support
~500 paying users is enough to clear $10k MRR, and small enough that a solo
operator can support it.

## How coding automates it

- **Discovery automation**: scrape AppSumo / Product Hunt / G2 / Reddit / niche
  forums for complaints → LLM cluster them → surface underserved verticals.
- **MVP build**: Next.js / Django / FastAPI scaffold + Stripe + auth +
  email-loop. Repos like `marc-lou/ship-fast` make this a one-weekend job.
- **Onboarding**: reverse-trial, magic-link auth, automated dunning.
- **Support**: vector-search the docs + ticket history; an LLM drafts replies
  for human review.
- **Marketing**: SEO pages auto-generated per vertical sub-niche; programmatic
  comparison pages; sponsored newsletter placements.

## Evidence / Numbers

- Marc Lou publicly disclosed ~$85k/mo in 2024 from ~6 micro-SaaS products
  ("ShipFast", "Gumroad-Landing-Page", etc.), see his tweet history and
  MarcLou.substack.com.
- MicroConf talks routinely cite $5k–$20k MRR as the realistic ceiling for a
  single micro-SaaS without paid ads.
- Kill: ~70% of micro-SaaSes never reach $100 MRR (IndieHackers data, ~2022).
  The median published revenue on IndieHackers is below $1k/mo — but those are
  survivors publishing.

## Cold-start plan

1. Spend 1 week scraping forums for "I wish X existed" complaints — output a
   ranked list of 10 verticals.
2. Pick one where you have **some** domain knowledge (avoids needing 100 hours
   of interviews).
3. Build absolute-minimum MVP in 7–14 days. No Stripe Atlas bloat, just
   Stripe Subscriptions + Next.js.
4. Launch on PH + IndieHackers + 2 niche subreddits. Price high initially
   ($49/mo), drop to $19 if no traction after 30 days.
5. Hit 5 paying customers before adding features.

## Risks & gotchas

- **Customer support eats your life** if you skip the "pick a vertical I
  understand" step. Generic tools → every user is a different shape of edge
  case.
- **Stripe fraud + chargebacks** on low-quality niches (dropshippers,
  "guru" customers) can kill your account. Vet verticals for refund-friendliness.
- **Feature creep**. The discipline is to say no for the first 90 days.
- **Platform risk** for distribution: PH rank decay, Reddit shadowbans.

## Verdict

Validate next. The scoring is honest: 4 effort because ongoing customer
support and marketing always take longer than expected. Skill 4 because you
need to ship fast, handle billing edge cases, and write copy. If I had to pick
one path and go all-in, this is it.