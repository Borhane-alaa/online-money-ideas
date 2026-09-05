# 2026-09-05 — 7-day market analysis

## What I did

- Refreshed market evidence for the 3 top candidates:
  - Privacy analytics (#20): scraped competitor pricing (Plausible,
    Fathom, Pirsch, Simple Analytics). Pirsch undercuts at $6/mo.
  - Mobile dev utility (#19): queried iTunes Search API for 6
    developer-tool keywords. Confirmed **~95% of "dev utility" apps in
    these slices are free**, and the few paid ones are at $1.99–$9.99.
    Top paid utility is Network Analyzer Pro ($3.99, 9,108 reviews, 4.8★)
    — a 9-year-old compounding winner.
  - Creator-niche micro-SaaS (#21): confirmed IndieHackers has a
    creator-economy category; PixelPeeper (HN 35567822) is the canonical
    proof point at $2k/mo after 6 years.

- Wrote `/research/runs/06-market-analysis/07-day-market-analysis.md`
  with side-by-side scorecard and ranked recommendation.

## Ranked recommendation

1. **#19 mobile dev utility on App Store** — first pick
2. **#21 creator-niche micro-SaaS** — pivot if mobile is wrong shape
3. **#20 privacy-first analytics** — wrong shape for 7 days, move to 30-day build

## Why #19 over the other two

- Publisher account already paid = lowest cash + time friction to ship
  (Android path is unblocked; iOS still needs $99 Apple Developer).
- **Distribution problem is bounded.** App Store SEO + 1 HN launch =
  most of the GTM. Privacy analytics depends on months of SEO;
  creator-niche depends on luck in a subreddit.
- **Ceiling is highest in the 12-month realistic window.** Solo dev
  utility at $5k–$20k MRR is well-documented (Proxyman iOS, PlaylistAI,
  HTTP Toolkit); $100k+ ARR privacy analytics takes 3+ years of SEO.
- Risk profile is cleanest: ongoing value, no LLM-disruption exposure
  per idea #22 risk register, low maintenance tax.

## What I am explicitly NOT recommending for the 7-day window

- #13 Chrome extension — directly parallel to #19 in distribution shape.
  Build #19 first; add Chrome in week 8 if I love it.
- #24 extension-monetization infra — only matters after #13 exists.
- #25 acquire-existing — wrong shape for 7 days (needs capital +
  sourcing, not code).

## Decisions made today

- **#19 is the bet.** I'm recording it here so when the user asks me
  to start the operational plan, I don't re-litigate the choice.
- The 7-day plan in the analysis is:
  - Day 1: pick wedge + start Xcode project
  - Day 2-3: MVP (capture + decode + paywall via StoreKit 2)
  - Day 4: Android equivalent or iOS polish
  - Day 5: App Store submission (screenshots, metadata)
  - Day 6: TestFlight to 10 dev friends
  - Day 7: Soft-launch (HN + r/iOSProgramming + personal network)

## Open questions for the user (next turn)

1. Confirm #19 vs. #21 vs. #20.
2. If #19: which wedge? (My recommendations are below.)

### Recommended wedges for #19 (mobile dev utility)

| wedge | rationale | risk |
|-------|-----------|------|
| **GraphQL debugger for iOS** | high-velocity stack, no clear native winner, dev pays $5/mo for a tool that saves them 1h/wk | very narrow |
| **LLM-call HTTP capture for iOS** | new category, every LLM dev needs this, no incumbent | novel, uncertain demand |
| **Webhook tester / sender for iOS** | older problem, real recurring need, few iOS-native options | medium saturation |
| **Postgres client for iOS (PG Orbit adjacent)** | developer-utility proven revenue, but already has PG Orbit | medium |

## Next action (waiting on user)

Wait for confirmation of the choice + wedge. Once confirmed, produce
the operational plan: file tree, build commands, store-submission
checklist, day-7 launch post draft.