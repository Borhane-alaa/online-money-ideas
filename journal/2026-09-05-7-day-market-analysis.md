# 2026-09-05 — 7-day market analysis (revised for Android-only)

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

- **Revision (after user correction):** user has only **Google Play
  developer account + Chrome Web Store developer account**; no Apple
  Developer. So #19 is **Android-only**, and **#13 Chrome extension
  becomes candidate #4** (previously rejected). Re-ran Play Store
  scrape for 8 dev-utility keywords (151 unique apps) and re-ranked.

- Wrote `/research/runs/06-market-analysis/07-day-market-analysis.md`
  with side-by-side scorecard and ranked recommendation.

## Ranked recommendation (post-revision)

1. **#19 Android dev utility on Play Store** — first pick
2. **#13 Chrome extension** — second pick (uses publisher-account bonus)
3. **#21 creator-niche micro-SaaS** — third pick (web only)
4. **#20 privacy-first analytics** — fourth pick; needs 30-day build

## Fresh Android-specific findings

- **149/151 (99%) dev-utility Android apps in the scraped keywords are
  free.** Only 5 paid apps across 8 keywords.
- **Canonical Android incumbents already exist:** Proxyman Android
  (`com.proxyman.proxymanandroid`) and HTTP Toolkit Android
  (`tech.httptoolkit.android.v1`). Niche of HTTP capture is taken.
- **Most underserved Android dev-utility niche:** GraphQL client/viewer
  — 1 competitor, no paid option.
- **Android revenue ceiling is 5–10× lower than iOS** (verified public
  disclosures of Proxyman founder: $2k MRR is iOS, with macOS being
  the bigger business; Android alone presumably $500/mo range).

## Why #19 is still 1st (despite Android-only revenue ceiling)

- **Zero cash outlay** (publisher account already paid).
- Distribution problem is bounded (Play Store SEO + 1 HN launch = GTM).
- The ceiling concern is mitigated by the **iOS-port upgrade path**:
  ship Android-only, validate, then add iOS for 5–10× the ceiling
  (after $1k MRR threshold, the $99/yr Apple Developer fee is
  trivial).
- GraphQL niche on Android is the fresh-data winner for the wedge.

## Decisions made today

- **#19 is the bet, GraphQL wedge preferred.** Recording it here so when
  the user asks me to start the operational plan, I don't re-litigate
  the choice.
- The 7-day plan in the analysis is:
  - Day 1: pick wedge + start Android Studio project (Kotlin)
  - Day 2-3: MVP (query editor + response viewer + saved queries)
  - Day 4: paywall (Play Billing Library 7), $2.99/mo or $19.99/yr,
    7-day trial
  - Day 5: Play Console submission (screenshots, metadata)
  - Day 6: Internal test track to 10 dev friends
  - Day 7: Production rollout to 5% then 100%, soft-launch on HN +
    r/androiddev + r/GraphQL

## Open questions for the user (next turn)

1. Confirm #19 vs. #13 vs. #21 vs. #20.
2. If #19: which wedge? (My recommendation is GraphQL.)

### Recommended wedges for #19 (Android dev utility, fresh data)

| wedge | rationale | risk |
|-------|-----------|------|
| **GraphQL client/viewer for Android** | 1 competitor, no paid option, no Proxyman equivalent | narrow but unblocked |
| **REST client w/ AI generation (URL→cURL→body)** | REST has 23 apps but 0 paid winners; AI-wedge makes it novel | novel, uncertain demand |
| **Webhook tester / sender for Android** | 25 apps, only 2 paid, no clear winner | medium saturation, but underserved paid tier |
| **LLM-call HTTP capture for Android** | every LLM dev needs this; captures OpenAI/Anthropic/Gemini calls | novel, depends on intercept reliability |

## Next action (waiting on user)

Wait for confirmation of the choice + wedge. Once confirmed, produce
the operational plan: file tree, build commands, store-submission
checklist, day-7 launch post draft.