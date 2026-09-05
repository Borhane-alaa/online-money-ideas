# 2026-09-05 — Vault initialized

## What I did

- Created `/home/alaa/Documents/projects/online-money-ideas/`.
- Created GitHub repo `Borhane-alaa/online-money-ideas` (public).
- Wrote README + IDEAS.md (the schema + master table) + .gitignore.
- Wrote 15 idea files spanning the major categories:
  saas, content, marketplace, automation-services, data-products,
  info-products, tools.
- Explicitly dropped 4 ideas (proxy reselling, AI stock photo, Reddit
  lead scraping, prompt-pack shelf-life caveats).

## Decisions made today

- **Repo name**: `online-money-ideas` (kebab-case, matches existing
  project naming).
- **Scope rules**: legit + code-automatable + solo-friendly + reproducible.
  These are non-negotiable. Anything violating gets dropped.
- **Status values**: `ship-now | validate-next | back-burner | dropped`.
- **Scoring system**: 4 axes (effort, skill, ceiling, risk), all 1–5.
  Conservative — influencer-floor-talk is excluded.

## Initial shortlist (validate-next)

The 9 ideas marked `validate-next` are candidates to actually pursue:

1. micro-saas-niche-vertical
2. api-reseller-open-data
3. chrome-extension-freemium
4. web-scraping-as-service
5. youtube-short-automation
6. newsletter-curator-bot
7. open-source-sponsorship
8. gumroad-dev-templates
9. ebook-prompt-pack (with shelf-life caveat)
10. twitter-thread-automation

Of these, **micro-SaaS** is the highest-ceiling bet but needs vertical
discovery work first. **Chrome extension** is the underrated lane — I want
to explore this seriously next week.

## What I'm NOT doing (yet)

- I am NOT going to ship every idea here. That would be scope creep.
- I am NOT going to write code today beyond this commit. Tomorrow or next
  session I pick one and run a 14-day MVP test.

## Next action

- Pick the top 2 verticals to validate for micro-SaaS using the
  discovery automation outline in `01-micro-saas-niche-vertical.md`.
- Decide between Chrome extension #13 and micro-SaaS #01 as the first
  MVP bet.