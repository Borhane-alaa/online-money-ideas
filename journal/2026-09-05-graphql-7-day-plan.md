# 2026-09-05 — #19 GraphQL wedge locked: 7-day operational plan

## Decision

User picked **#19 mobile dev utility + GraphQL wedge + Android-only**.
7-day build to Play Store production.

## What I did

- Re-ran Play Store scrape specifically for 5 GraphQL keywords
  (graphql_client, graphql_viewer, graphql_ide, graphql_query,
  apollo_client).
- **Across 66 unique apps found in those searches, only ONE is a
  dedicated GraphQL client:** `info.camposha.graphql_viewer` by
  Clement Ochieng. **50+ installs, free, no IAP, last updated May
  2026.** Niche is wide open.
- Pulled the competitor's full Play Store detail page and reviewed
  its feature list. The MVP scope below is parity + small polish
  on top.
- Wrote the operational plan at
  `/research/runs/06-market-analysis/19-graphql-7-day-plan.md`:
  - Day-by-day schedule (Day 1 scaffold → Day 7 launch).
  - MVP feature list (hard cut, do NOT add to it in week 1).
  - File tree (~2,500 LOC target).
  - Pricing decision (Free / $2.99 mo / $19.99 yr / $39.99 lifetime).
  - Play Store listing copy.
  - Pre-launch tester list + email template.
  - Launch post text for HN, r/androiddev, r/GraphQL.

## Pricing decision (final, locked)

| tier | price | includes |
|------|------:|----------|
| Free | $0 | 2 endpoints, 10 saved queries, 7-day history |
| Monthly | **$2.99/mo** | unlimited everything |
| Yearly | **$19.99/yr** | unlimited, ~44% savings |
| Lifetime | **$39.99** | one-time, unlimited |
| Trial | 7 days | full Pro, auto-converts to monthly |

Rationale: $2.99/mo matches the Play Store dev-utility sweet spot
(API Tester Pro $4.09, DC Webhook Pro $7.99, Health Connect Webhook
$14.99). Yearly nudges annual conversion. Lifetime captures the
"I use this daily" segment. 7-day trial reduces purchase friction.

## What's NOT in v1 (deliberate omissions)

- Subscriptions / WebSockets (over-engineering)
- AI query generation (adds cost, doesn't address the wedge)
- Cloud sync / accounts (kills "no account needed" differentiator)
- iOS (waits until $1k MRR clears the $99/yr Apple Dev fee)
- Postman collection import (defer to v2 based on user demand)
- Tablet-optimized layout (defer to v2)

## Open for the user

Before Day 1, three things need to happen:

1. **Pick a name** — top recommendations are "QuokkaQL — GraphQL
   Client" or "GraphQL Pocket". Lock it down so you can reserve the
   Play Console app slot.
2. **Verify the Play Console account** (sign in, confirm you can
   create new apps).
3. **Install Android Studio** (or update to latest) and verify a
   hello-world APK builds.

Once those are confirmed, I can produce the actual starter project
(structure files, manifest, billing library setup, etc.) or just
hand you this plan to execute yourself.

## Sources for the plan

- Play Store search data scraped 2026-09-05: 5 GraphQL-related
  keywords (66 unique apps found, 1 dedicated GraphQL client).
- Competitor detail page: info.camposha.graphql_viewer, 50+ installs,
  free, last updated May 2026.
- Pricing benchmark: 4 paid Android dev utilities ($4.09–$164.99).