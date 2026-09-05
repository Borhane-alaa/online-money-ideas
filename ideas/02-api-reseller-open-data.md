---
title: API reseller for open data
slug: api-reseller-open-data
status: validate-next
added: 2026-09-05
effort: 3
skill: 3
ceiling: 3
risk: 2
verdict: Good first $1k–$5k/mo business, low stress, hard to grow past that.
tags: [data-products, saas]
---

## Premise

Take data that's technically free (government open-data portals, public SEC
filings, Wikipedia, OpenStreetMap, public court records, public Twitter/X
research APIs, BLS / Eurostat feeds) and wrap it in a clean REST API + nice
docs + a paid tier. Charge $0–$499/mo based on rate limits. Examples:
- `apify.com` (started as scraper marketplace)
- `birds-eye-view.co`
- `serpapi.com` (Google results, technically reverse-engineered)

## How coding automates it

- A wrapper layer around the free source (caching, schema, docs, billing).
- Cron jobs to refresh the underlying dataset.
- Stripe + tiered rate limiting.
- Auto-generated SDKs (openapi-generator) so customers paste a snippet.

## Evidence / Numbers

- `serpapi.com` is publicly disclosed at $7-figures/year.
- Most indie API resellers sit at $1k–$10k MRR.
- SaaSHub and api.market list ~100s of small resellers, mostly in this band.

## Cold-start plan

1. Pick a free source with **steady demand** (e.g. SEC EDGAR, BLS labor
   stats, USAspending.gov, ECB FX rates, OpenStreetMap POIs).
2. Build the API + landing page. Use FastAPI + Stripe in <2 weeks.
3. List on `apify.com`, `rapidapi.com`, ProductHunt, and `/r/webscraping`.
4. SEO the docs — most API reseller revenue comes from organic dev searches.
5. Add a "build your own" doc so people can fork your wrapper if needed (free
   marketing).

## Risks & gotchas

- **Free data sources break their TOS** without warning (Twitter's free tier is
  already gutted; SEC EDGAR publishes rate limits). Always have a fallback.
- **Commoditization**: if anyone can hit the source, what's the moat? Moat =
  reliability, schema, docs, uptime. Not the data.
- **Customer concentration**: most indie API customers are bots. One bot
  operator going down can be 50% of MRR.
- **Data licensing**: some "open" sources prohibit commercial resale (some EU
  datasets under CC-BY-NC, some city portals with no commercial clause). Read
  the actual license.

## Verdict

Validate next. This is the lowest-friction business on the list — but the
ceiling is real. Good stepping stone to a proper micro-SaaS or data company.