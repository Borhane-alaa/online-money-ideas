---
title: LLM-curated niche newsletter
slug: newsletter-curator-bot
status: validate-next
added: 2026-09-05
effort: 4
skill: 3
ceiling: 3
risk: 2
verdict: Proven model — Lenny's Newsletter / TLDR / Trends.co all run this. Effort lives in distribution, not writing.
tags: [content]
---

## Premise

Run a curated, weekly newsletter in a niche (AI engineering, dev tooling,
indie SaaS, Postgres news, embedded hardware, etc.). Charge for sponsor slots
and / or a premium tier.

## How coding automates it

- Crawl sources (RSS, arXiv, X lists, GitHub trending, HN).
- LLM dedupes, ranks, and drafts blurb per item.
- Human spends 30 min editing the draft.
- ESP (Beehiiv, Substack, ConvertKit) handles delivery + subscribe.
- Stripe on the backend for paid tier.

## Evidence / Numbers

- Trends.co (trends.vc) disclosed $250k+/yr from a single weekly newsletter
  with one operator.
- Lenny's Newsletter: $1M+/yr from 500k+ subs at the public tier.
- TLDR: 1.5M subs, multi-revenue (sponsors, paid tier, hiring board).

## Cold-start plan

1. Pick a niche where you already read everything anyway.
2. Manual for first 4 issues to lock the voice. Don't over-engineer.
3. After 4 issues, build the scrape + draft pipeline.
4. Submit to newsletters directories, tweet each issue, post to relevant
   subreddits.
5. Sponsorships kick in around 5–10k subs (typically 6–12 months).

## Risks & gotchas

- **Subscribers don't equal revenue**. Median sponsor rate is $10–$50 CPM,
  which means 10k subs = $1k–$5k per sponsor slot. Need ~25k subs to live on
  one newsletter.
- **Burnout** — the personal-brand version is non-automatable. The
  curator-bot version needs steady editorial control or it goes generic.
- **Deliverability**: warm up your sending domain, SPF/DKIM/DMARC, watch
  spam rates.

## Verdict

Validate next. Highest-leverage option if you already have ANY audience
(Twitter, GitHub stars, conference circuit). Without audience, it's a 12-month
ramp before sponsorships.