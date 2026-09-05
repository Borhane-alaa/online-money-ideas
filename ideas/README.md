# Ideas Index

One Markdown file per idea. Filename is a slug. Each file uses the shared
schema below.

## File schema

```yaml
---
title: Human-readable name
slug: kebab-case-id
status: ship-now | validate-next | back-burner | dropped
added: 2026-09-05
effort: 1-5
skill:  1-5
ceiling: 1-5
risk:   1-5
verdict: one-line take
tags: [category, ...]
---
```

Then sections: `## Premise`, `## How coding automates it`,
`## Evidence / Numbers`, `## Cold-start plan`, `## Risks & gotchas`,
`## Verdict`.

## Categories

- `saas` — micro-SaaS products sold to niche B2B or prosumer audiences
- `content` — newsletters, blogs, YouTube, podcasts monetized via ads / sponsors
- `marketplace` — sell a product or service on a third-party marketplace
  (Gumroad, AppSumo, etc.)
- `automation-services` — sell automation-as-a-service to other businesses
- `data-products` — datasets, APIs, scrapers, feeds sold to other builders
- `info-products` — courses, templates, ebooks, paid communities
- `tools` — dev tools, browser extensions, CLIs that charge via license / SaaS
- `arbitrage` — pure code-mediated value transfer (price diff, lead-gen,
  affiliate routing) where allowed

## How scoring works

| score | effort | skill | ceiling | risk |
|-------|--------|-------|---------|------|
| 1     | <1 h/wk| can read docs | <$200/mo | platform-OK, no $$ at stake |
| 2     | 1–3 h/wk| comfortable dev | $200–$1k/mo | mostly platform-OK |
| 3     | 3–6 h/wk| solid dev (3+ yrs) | $1k–$5k/mo | some money + reputation risk |
| 4     | 6–12 h/wk| senior dev | $5k–$20k/mo | regulated / capital / brand |
| 5     | full-time | specialist (ML/MLOps/AI infra) | $20k+/mo | heavy reg / payments / capital |

## The list

| # | slug | status | effort | skill | ceiling | risk | one-liner |
|---|------|--------|--------|-------|---------|------|-----------|
| 1 | micro-saas-niche-vertical | validate-next | 4 | 4 | 4 | 2 | Tiny SaaS for one ignored vertical |
| 2 | api-reseller-open-data | validate-next | 3 | 3 | 3 | 2 | Bundle free public APIs behind a paid UX |
| 3 | affiliate-niche-comparison | back-burner | 3 | 2 | 2 | 1 | Code-generated comparison/review sites |
| 4 | gumroad-dev-templates | validate-next | 2 | 2 | 2 | 1 | Sell small dev templates on Gumroad |
| 5 | youtube-short-automation | validate-next | 4 | 3 | 4 | 3 | Code-driven faceless YouTube Shorts channel |
| 6 | newsletter-curator-bot | validate-next | 4 | 3 | 3 | 2 | LLM-curated niche newsletter |
| 7 | proxy-reseller-fleet | dropped | 5 | 5 | 4 | 5 | Resell residential proxies — heavy abuse risk |
| 8 | web-scraping-as-service | validate-next | 3 | 3 | 3 | 2 | Niche data extraction sold to non-tech clients |
| 9 | saas-boilerplate-flip | back-burner | 2 | 3 | 2 | 1 | Build + flip starter SaaS kits |
| 10 | ai-workflow-consultant | back-burner | 3 | 3 | 3 | 2 | Wire LLMs into SMB workflows, charge setup + retainer |
| 11 | stock-photo-microstock | dropped | 5 | 4 | 2 | 3 | AI-generated stock — platform risk + low payouts |
| 12 | reddit-lead-pipeline | dropped | 3 | 3 | 3 | 4 | Scrape intent → cold email — fragile, ToS gray |
| 13 | chrome-extension-freemium | validate-next | 3 | 3 | 3 | 2 | Niche Chrome extension w/ freemium paywall |
| 14 | saas-pricing-page-teardown | back-burner | 2 | 2 | 2 | 1 | Sell competitor-pricing research reports |
| 15 | ebook-prompt-pack | validate-next | 2 | 2 | 2 | 1 | Curated prompt packs on Gumroad/Lemon Squeezy |
| 16 | twitter-thread-automation | validate-next | 3 | 2 | 2 | 2 | LLM-driven niche thread accounts |
| 17 | open-source-sponsorship | validate-next | 2 | 3 | 3 | 1 | Build OSS dev tool, get GH Sponsors |

(Live list, see the per-idea files for full detail.)