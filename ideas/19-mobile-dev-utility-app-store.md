---
title: iOS / mobile dev utility on App Store
slug: mobile-dev-utility-app-store
status: validate-next
added: 2026-09-05
effort: 4
skill: 3
ceiling: 4
risk: 2
verdict: Real money. Subscription on App Store works. Less "race to the bottom" than web micro-SaaS — Apple/Google are not eating your niche.
tags: [tools, saas]
---

## Premise

Build a small, paid iOS (or Android, or Mac) utility for a specific developer
audience. Charge via App Store subscriptions. Examples: HTTP-traffic
inspectors, JSON viewers, SQL clients, REST testers, network tools.

## How coding automates it

- Native iOS/macOS dev. Swift / SwiftUI for iOS.
- App Store handles discovery, billing, refunds (minus its 30% cut).
- Updates are a small concern once v1 ships; long-tail revenue compounds.
- No web hosting, no Stripe Atlas, no server bills.

## Evidence / Numbers

- **Proxyman / Proxyman for iOS** (nghiatran_uit, HN 35567822): ~$2k/mo MRR
  on iOS alone (macOS version is the bigger business). $4.99/mo or $39.99/yr
  or $99 lifetime.
- **HTTP Toolkit** (pimterry, HN 35567822): $2k+/mo; now full-time for the
  founder.
- **PlaylistAI** (bbauman, HN 35567822): $2.5k MRR iOS app, "hit $2k in 2
  weeks" after launch in January 2024 (consumers, not dev).
- Apple's dev-tools category is famously concentrated: small list of
  premium apps that have stayed paid for years.

## Cold-start plan

1. Pick a desktop dev tool you already use, and look for the equivalent
   pain point on iOS.
2. Build a polished native app. Don't cross-compile a web app into a
   Capacitor wrapper — the store ranking algorithms punish that.
3. Price at $4.99/mo or $39.99/yr (the App Store sweet spot for utility).
5. Submit, expect 1–3 day review, expect first rejection cycle.
6. Promote on Product Hunt + relevant subreddits + your network.

## Risks & gotchas

- **Apple's 30% cut** (15% for small devs <$1M/yr, but you still pay it).
- **App Store review** is opaque and can reject without explanation;
  battle-test before launch.
- **Cross-platform tax**: building once for iOS+macOS is doable but adds
  maintenance. Pick one.
- **Discoverability on App Store** is its own SEO game. Listings with
  screenshots + good copy win.

## Verdict

Validate next. Higher ceiling than the average indie SaaS because the App
Store distribution problem is bounded. Real revenue proof.

## Sources

- HN thread 35567822 (Ask HN: Side project >$2k monthly revenue):
  - nghiatran_uit (Proxyman iOS)
  - pimterry (HTTP Toolkit)
  - bbauman (PlaylistAI)