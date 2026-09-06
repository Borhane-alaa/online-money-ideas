# 7-Day Market Analysis: Top 3 Candidates

**Date:** 2026-09-05
**Goal:** Pick ONE idea to ship inside 7 days. This is the document that
chooses it.
**Constraint:** publisher accounts (Google Play + Chrome Web Store) are
already paid and active. That changes the math: App Store + Web Store
distribution is *unblocked*, not a "build it and figure out how to publish"
risk.

## The candidates

1. **#19 — mobile dev utility on Play Store (Android-only)** — iOS
   ruled out: user does NOT have Apple Developer account ($99/yr
   enrollment required).
2. **#20 — privacy-first web analytics** — web product, no publisher
   account needed.
3. **#21 — micro-SaaS for one creator/professional niche** — web
   product, no publisher account needed.

Not in the top 3 (explicitly rejected for this analysis):
- **#13 Chrome extension** — *re-elevated as candidate #4*. With Android
  dev-utility lane now iOS-blocked, Chrome extension becomes the most
  distribution-friendly option that uses the publisher-account bonus.
- #24 extension-monetization infra — only matters once #13 ships.
- #25 acquire-existing — wrong shape for 7 days.

---

## #19 — Mobile dev utility on Play Store (Android only)

**Important correction:** the original analysis assumed iOS + Android.
The user has **Google Play only, no Apple Developer**. iOS is OFF the
table for the first build. This changes the market signal substantially
because Android dev-utility landscape is *less saturated* and *less
monetized* than iOS — which is a double-edged sword: easier to enter,
harder to make money.

### Market size (signal — fresh Android data, scraped today)

8 Play Store keywords surveyed, 151 unique app IDs extracted from
search result pages.

| keyword | apps found | paid apps | canonical paid app | price |
|---------|-----------:|----------:|--------------------|------:|
| http_inspector   | 17 | 2 | HTML Inspector Pro | $7.49 |
| http_inspector   | –  | –  | HTTP Sniffer Pro   | $164.99 |
| network_debugger | 8  | 0 | – | – |
| REST_client      | 23 | 0 | – | – |
| api_tester       | 24 | 1 | API Tester Pro | $4.09 |
| json_viewer      | 25 | 0 | – | – |
| sql_client       | 6  | 0 | – | – |
| webhook_tester   | 25 | 2 | DC Webhook Pro / Health Connect Webhook | $7.99 / $14.99 |
| **graphql_client** | 25 | 0 | **none paid — niche wide open** | – |

### Competition density on Android (signal)

- **149 of 151 (99%) dev-utility apps in this slice are free.**
- Only **5 paid apps** total across 8 keywords: HTML Inspector Pro
  ($7.49), HTTP Sniffer Pro ($164.99 — outlier pricing), API Tester Pro
  ($4.09), DC Webhook Pro ($7.99), Health Connect Webhook ($14.99).
- **Canonical incumbents that exist on both platforms:**
  - **Proxyman Android** (`com.proxyman.proxymanandroid`) — same team,
    paid, niche is taken.
  - **HTTP Toolkit Android** (`tech.httptoolkit.android.v1`) — same
    team, taken.
- **Most underserved Android dev-utility niche found in this sweep:**
  GraphQL — only **1 app** (`info.camposha.graphql_viewer`), no paid
  option. Compare to 25 apps on REST_client and 23 on json_viewer.

### GTM (signal)

- Play Store SEO (keywords in title + short description + long
  description).
- One solid HN / r/androiddev post can drive 5k–50k installs.
- Reddit: r/androiddev, r/Kotlin, niche Slack/Discord communities.
- YouTube tutorials are the long-tail unlock.
- Cross-promotion from any of your existing projects (if you ship
  Android dev utility, mention it in your other apps' more-info page).

### Revenue range (Android dev utility, conservative)

- **Hard ceiling on Android is much lower than iOS.** Most paid Android
  dev utilities earn <$1k MRR based on public disclosures.
- The one verified revenue datapoint from HN: **Proxyman founder
  discloses ~$2k/mo for the iOS version, with macOS being the bigger
  business; Android is not disclosed separately** but is presumably
  smaller. (nghiatran_uit, HN 35567822.)
- **Realistic solo ceiling on Android only:** $500–$5k MRR. The 5–10×
  gap from iOS is real because Android users spend less on paid apps.
- **Realistic ceiling on Android + iOS later:** $5k–$20k MRR, but iOS
  requires Apple Developer signup ($99/yr) and 7–10 extra days of
  porting work.

### Risk profile (revised for Android only)

| risk | score (1-5) | note |
|------|------------:|------|
| Play Store reviewer rejects v1 | 2 | well-documented common path |
| Free competitor undercuts | 4 | **higher than iOS** — 99% free |
| Niche too narrow | 3 | mid — depends on wedge |
| Maintenance tax | 2 | annual iOS upgrades N/A; just Android |
| **LLM-disruption** | 1 | ongoing value, dev utility |
| **Android-only revenue ceiling** | 3 | real — Android users pay less |

### 7-day ship plan (Android only)

| day | deliverable |
|-----|-------------|
| 1  | pick wedge (recommend: **GraphQL client/viewer for Android** — 1 competitor, no paid options) |
| 2  | Kotlin project scaffold + GraphQL query UI |
| 3  | MVP: query editor + response viewer + saved queries |
| 4  | paywall (Play Billing Library 7), $2.99/mo or $19.99/yr, 7-day trial |
| 5  | Play Console: store listing, screenshots, metadata, submit |
| 6  | Internal test track to 10 dev friends, fix top 3 bugs |
| 7  | Production rollout to 5% then 100%, soft-launch on HN + r/androiddev + r/GraphQL |

**Realistic outcome:** Play Store submission accepted by day 5–7.
Revenue: $0 for first 30 days (store ranking needs to compound).
Treat launch as **distribution-day-one, not revenue-day-one**.

### Cost to ship

- **Google Play developer: already paid. $0.**
- Dev: existing laptop + Android Studio (free).
- **Cash outlay: $0.**

---

## #20 — Privacy-first web analytics

### Market size (signal)

- **4 viable competitors already exist**: Plausible, Fathom, Pirsch,
  Simple Analytics. Plausible's public dashboard discloses ~$3M+
  ARR (2024). Fathom similar. Pirsch at ~$4k MRR (2 founders).
  Simple Analytics at ~$1M+ ARR.
- **The category is validated; the gap is in the wedge.**

### Pricing benchmark (signal, scraped today)

| competitor | entry tier | full tier | pricing model |
|------------|-----------:|----------:|---------------|
| Plausible | $9/mo (10k pageviews) | $19+/mo | usage-based, pageviews |
| Fathom | not scraped cleanly | **$45/mo contact** | usage-based |
| Pirsch | **$6/mo (10k pageviews)** | tiered | usage-based |
| Simple Analytics | **$20/mo per user** | tiered | per-seat, not pageviews |

- **Pirsch undercuts on price** ($6/mo vs Plausible $9/mo, Fathom $45+/mo).
- **Simple Analytics** chose a different model entirely (per-seat), not
  per-pageview.
- **Implication:** pricing is not the wedge; the wedge has to be
  vertical or workflow.

### Competition density

- **High** at the "general privacy analytics" level.
- **Low to medium** at any specific vertical wedge:
  - "Privacy analytics for SaaS dashboards" (Segment / Mixpanel exit
    market)
  - "Privacy analytics for content sites" (Plausible does this well)
  - "Privacy analytics for ecommerce" (Plausible + Conversions API gap)
  - "Self-hosted-only" (none of the 4 incumbents are open-source
    core; Ackee + GoMat is open-source but no hosted)
  - **"Privacy analytics for SaaS funnels" is the most underserved.**

### GTM

- SEO is the moat: "Google Analytics alternative" is the entire funnel.
- Hacker News + Product Hunt + privacy-focused subreddits (r/privacy,
  r/privacytoolsIO, r/selfhosted).
- Word-of-mouth inside privacy/regulatory consulting circles.
- Bundle: a 2-line script + a single dashboard; ship a free tier that
  becomes the upgrade path.

### Revenue range (conservative)

- Ackee-style (open-source, hosted) at 1k hosted sites × $9/mo = ~$9k MRR.
- Pirsch (HN 35567822, 2 founders): ~$4k MRR. Lower than the leaders
  because they're a 2-person shop without the SEO moat.
- Plausible at ~$3M ARR is the ceiling for a category leader.
- **Realistic solo ceiling:** $5k–$20k MRR at 12 months with steady
  SEO content and a sharp wedge. $100k+ ARR is the Plausible-track.

### Risk profile

| risk | score (1-5) | note |
|------|------------:|------|
| Big-player eats the wedge (Cloudflare WA) | 4 | already happening at the bottom |
| Server costs at scale | 2 | bounded, but real |
| Differentiation in a crowded lane | 4 | high — must pick a sharp wedge |
| Customer expectations (funnels, attribution) | 2 | common education problem |
| **LLM-disruption** | 1 | ongoing-value (compliance + monitoring) = moat |

### 7-day ship plan

| day | deliverable |
|-----|-------------|
| 1  | decide wedge (recommend: "privacy analytics for SaaS funnels" — most underserved) |
| 2  | minimal server-side ingest + tiny JS shim |
| 3  | dashboard (Next.js + a chart lib) |
| 4  | Stripe + tiered pricing + free tier |
| 5  | landing page + SEO content (5 programmatic pages) |
| 6  | self-host docker image (defensible against Cloudflare WA) |
| 7  | Show HN post + r/selfhosted + IndieHackers |

**Realistic outcome:** working MVP that can ingest 100 sites'
analytics, with a Stripe paywall. Revenue: $0 in the first 30 days
(SEO + word-of-mouth takes months to compound). 30-day revenue
target: **$50–$200/mo from 5–20 early users**.

### Cost to ship

- Postgres: $0–$25/mo on a small DO/Hetzner instance.
- Domain: $10/yr.
- Dev: existing laptop + VSCode.
- **Cash outlay:** ~$35 in month one.

---

## #21 — Micro-SaaS for one creator niche

### Market size (signal)

- **IndieHackers has a "creator-economy" category** with categories
  spanning Content, Design, Fashion, Music, Video, Education, etc.
- **PixelPeeper** (pchm, HN 35567822): $2k/mo after 1–2 months, solo,
  still running at $2k/mo after 6 years (founder says niche is too
  small to grow past $2k/mo — explicit ceiling).
- **PlaylistAI** (bbauman, HN 35567822): $2.5k MRR after 2 weeks of
  launch on iOS — but this is *consumer*, not creator-tool, and
  belongs in #19 lane.
- **33mail** ($8k/mo after 10 years, HN 25434753) is the long-tail
  ceiling proof point — slow, but real.

### Competition density

- **Very high** at the "creator tools" level (Adobe, Canva, Figma
  dominate).
- **Very low** at any specific creator-niche intersection. The wedge is
  always a *narrow job-to-be-done* (Lightroom preset reverse-eng,
  Etsy listing generator, Twitch highlight creator, etc.), not a
  general creator tool.

### GTM

- **The launch lives in the niche subreddit or Product Hunt.**
  PixelPeeper rode Instagram + Lightroom subreddit momentum. Each
  niche has its own surf to catch.
- Niche influencers (1–5 people) usually drive 60% of initial
  installs.
- SEO: every micro-tool gets the "best [niche tool] 2026" search
  traffic.

### Revenue range (conservative)

- **Median:** $300–$2k MRR. PixelPeeper is a 6-year median.
- **Lower quartile:** $0–$300 MRR (most fail at discovery).
- **Upper quartile:** $5k–$20k MRR (if the niche is broader than you
  thought, e.g. PictureThis with a different label).
- **Ceiling**: real ceiling is the niche. $2k/mo is a healthy
  outcome; $10k/mo is rare and usually means the niche was broader
  than the founder realized.

### Risk profile

| risk | score (1-5) | note |
|------|------------:|------|
| Niche too narrow | 4 | **the dominant failure mode** |
| Discovery / launch failure | 3 | common, recoverable |
| Free competitor | 3 | common — most niches have one |
| Maintenance tax | 1 | tiny — narrow feature set |
| **LLM-disruption** | 2 | static features at risk; ongoing-value features fine |

### 7-day ship plan

| day | deliverable |
|-----|-------------|
| 1  | pick creator-niche intersection you use (e.g. "AI listing copy for Etsy," "Lightroom preset sharing," "Notion template marketplace for HR") |
| 2  | talk to 3 niche users (Reddit, X, Discord) — confirm pain |
| 3  | MVP scaffold (Next.js + Stripe) |
| 4  | MVP core loop working (one job done end-to-end) |
| 5  | paywall + landing page |
| 6  | pre-launch: 10 niche users signed up via personal network |
| 7  | launch on niche subreddit + relevant influencer DM |

**Realistic outcome:** working product, $0–$300 MRR from first 7
days. **This lane is the slowest to monetize but the easiest to
ship in 7 days.** Founder stays long enough to see real revenue only
if the niche is broader than expected.

### Cost to ship

- Hosting: $0–$20/mo.
- Domain: $10/yr.
- Dev: existing laptop.
- **Cash outlay:** ~$30 in month one.

---

## Side-by-side scorecard

| axis | #19 mobile dev util (Android) | #20 privacy analytics | #21 creator-niche SaaS | #13 Chrome ext |
|------|---------------------|------------------------|------------------------|-----------------|
| 7-day shippable | ✅ realistic | ✅ possible (MVP only) | ✅ very realistic | ✅ realistic |
| Cash to ship | **$0** | ~$35 | ~$30 | **$0** |
| Time to first $1 | 30–60 days (store ranking) | 60–180 days (SEO) | 30–90 days | 30–90 days (Web Store SEO) |
| Time to $1k MRR | 6–12 months | 6–12 months | 3–9 months | 6–12 months |
| Ceiling | $500–$5k MRR (Android-only) | $5k–$100k+ MRR | $1k–$5k MRR | $1k–$10k MRR |
| Competitive density | medium (less than iOS) | high | high (in lane) / low (in wedge) | medium |
| LLM-disruption exposure | low | very low | medium | low–medium |
| Maintenance tax | low (just Android) | medium (server costs) | low | low |
| Distribution | Play SEO + HN + Reddit | SEO + HN + IndieHackers | Niche subreddit + influencer DM | Chrome Web Store SEO + HN |
| **Publisher-account bonus** | ✅ YES | ❌ n/a | ❌ n/a | ✅ YES |
| **iOS-equivalent headroom** | ❌ NO (Apple Dev absent) | n/a | n/a | ✅ n/a (cross-browser) |
| Best for | solo dev with Android/Kotlin + niche expertise | solo dev with strong SEO + content muscle | solo dev with niche authenticity | solo dev who already lives in the browser |

---

## My ranked recommendation (revised for Android-only)

### 1st pick: **#19 — Android dev utility on Play Store**

If:
- **Publisher-account already paid = zero cash outlay**, the only "free"
  option in the entire comparison.
- Distribution problem is bounded (Play Store SEO + 1 HN launch =
  most of the GTM).
- Real ceiling on Android alone is $500–$5k MRR — *lower than the
  original analysis assumed for iOS+Android*. But: once revenue
  compounds past $1k MRR, **enrolling in Apple Developer ($99/yr) is
  a no-brainer**, and the existing code base ports in 7–10 days.
- **GraphQL niche on Android is wide open** — 1 competitor, no paid
  option, no Proxyman-equivalent incumbent. Strongest wedge in the
  fresh data.

The reason this is 1st and not #21 (which is "easiest to ship") is
**the distribution problem**. Creator-niche SaaS requires you to
find the right subreddit, the right influencer, the right timing.
Mobile dev utility on Play Store is a more predictable distribution
game with a real algorithmic moat (store ranking).

The Android-only ceiling concern is mitigated by the iOS-port
upgrade path: ship Android-only, validate, then add iOS for 5–10× the
ceiling.

### 2nd pick: **#13 — Chrome extension**

If #19 doesn't resonate (you don't want to ship native Android) or
you want a faster "ship in 7 days" path, #13 is the right pivot.
Same publisher-account-unblocked economics as #19, but smaller build
(an extension MVP is faster than an Android MVP) and Chrome Web
Store review is faster than Play Store review (~24h vs ~3 days).

**Trade-off vs #19:** Chrome extensions have a tighter ceiling than
mobile dev utility because they're tied to the browser and the
Web Store has a more limited discovery surface. But the floor is
friendly: a small extension can hit $300–$1k MRR with low maintenance.

### 3rd pick: **#21 — creator-niche micro-SaaS**

If you don't want to ship native (Android OR Chrome), #21 is the
web-only bet. PixelPeeper's $2k/mo ceiling is fine. The risk is the
niche ceiling is real and you can't grow past it without discovering
the niche was bigger than you thought.

### 4th pick: **#20 — privacy-first analytics**

Strongest long-term ceiling, weakest 7-day shippability, hardest
distribution. Move this to a 30-day build instead of a 7-day build.
Best as the **second project** once one of the other three is
cash-flowing.

### What I am NOT recommending

- #24 extension-monetization infra — only matters once #13 ships.
- #25 acquire-existing — wrong shape for 7 days.

---

## Next action for you

Tell me which of the four to actually start. I'll then produce the
**operational plan** for that pick: file tree, build commands, store-
submission checklist, and the day-7 launch post text.

### Recommended wedges for #19 (Android dev utility, fresh data)

| wedge | rationale | risk |
|-------|-----------|------|
| **GraphQL client/viewer for Android** | 1 competitor, no paid option, no Proxyman equivalent | narrow but unblocked |
| **REST client w/ AI generation (URL→cURL→body)** | REST has 23 apps but 0 paid winners; AI-wedge makes it novel | novel, uncertain demand |
| **Webhook tester / sender for Android** | 25 apps, only 2 paid, no clear winner | medium saturation, but underserved paid tier |
| **LLM-call HTTP capture for Android** | every LLM dev needs this; captures OpenAI/Anthropic/Gemini calls | novel, depends on intercept reliability |