# 2026-09-05 — QuokkaQL: Days 2-7 shipped (full launch kit)

## What landed since the Day-1 journal

Day 2+3 (query editor + saved/history):
- `JsonTreeView` for the response viewer (indented, type-aware).
- `SavedAndHistorySheet` modal bottom sheet (Saved | History tabs).
- `EndpointDetailScreen` rewritten to use both, with a Save Query
  dialog and per-endpoint history appending.
- Helper `parseVariablesJson()` shared between the editor and the
  Run button.

Day 4 (billing + Pro gates):
- `BillingCatalog` holds the `StateFlow<List<ProductEntry>>` plus
  per-product price strings; subscribes via `BillingManager.catalog.state`.
- `BillingManager.launchProPurchase()` extension fn wires Play
  Billing's `launchBillingFlow` for both subs and one-time.
- Removed the stale inner `sealed interface ProductDetails` DTO —
  replaced by `BillingCatalog.ProductEntry`.
- `PaywallScreen` rewritten to consume the catalog and launch the
  purchase flow; reflects "You're Pro" when tier flips.
- `MainActivity` now refreshes the catalog ~250ms after Billing
  handshake completes.
- `SettingsScreen.onClearAll` now properly awaits the repo clears
  via a `CoroutineScope.launch`.

Day 5+6 (signing + submission):
- `scripts/generate-keystore.sh` — one-time keystore creation +
  prints env-var exports.
- `scripts/submit-internal-test.sh [--upload]` — builds a signed AAB
  and (optionally) pushes via the Google Play Android Publisher API
  using a service-account JSON.
- `scripts/promote-to-production.sh` — rollout helper.
- `scripts/SERVICE-ACCOUNT-SETUP.md` — full setup docs for the
  service account + Play Console role grant.

Day 7 (launch kit):
- `launch/hn-show-hn.txt` — ready-to-paste HN Show HN.
- `launch/r-androiddev.md` — Reddit post focused on lessons, not
  product.
- `launch/r-graphql.md` — Reddit post framed as a question about
  mobile-first GraphQL tooling.
- `launch/influencer-dm.txt` — DM template for niche dev influencers.
- `scripts/submit-hn.py` — HN Algolia submission helper. Requires
  the user to provide their HN `user=` cookie + Algolia key as env
  vars.

## Counts (final state)

- 22 Kotlin source files
- 4 launch markdown/text files
- 5 scripts (4 shell, 1 Python)
- 1 setup doc (SERVICE-ACCOUNT-SETUP.md)
- ~2,500 LOC Kotlin

## Repo + vault state

- `Borhane-alaa/quokkaql` — pushed, commit `01fd673` on origin/main.
  Working tree clean, local = remote.
- `Borhane-alaa/online-money-ideas` — vault updated with this
  journal entry. Working tree clean.
- `HANDOFF.md` written in the QuokkaQL repo so the next session
  picks up cleanly without re-deriving context.

## What is genuinely NOT done

These still need the user to run them on a real machine:

1. **Validate the Gradle build in Android Studio.** I have no Kotlin
   compiler or Android SDK on this host. The Kotlin is verified by
   static review only. First sync may surface small API drift in
   Compose Material3 icons / Compose 1.7 BOM 2024.10.01. Fixes
   will be one-line.
2. **Generate the keystore.** Run `scripts/generate-keystore.sh`
   on Day 5.
3. **Create Play Console products.** Three in-app products
   (monthly / yearly / lifetime subscriptions, lifetime one-time)
   need to be created in Play Console before the purchase flow
   actually opens.
4. **Submit to internal testing.** Run
   `scripts/submit-internal-test.sh --upload` after the service
   account is configured per `SERVICE-ACCOUNT-SETUP.md`.
5. **Post the launch content.** Day 7. HN Show HN is the highest-
   leverage single action; do that before the Reddit cross-posts.

## Caveats the user should know

- The Play Billing signature-verification path assumes minimal R
8
   obfuscation. If you enable full obfuscation, you'll likely need
   additional `-keep` rules in `app/proguard-rules.pro` for the
   billing-client SDK.
- `Icons.AutoMirrored.Filled.ArrowBack` requires Compose Material3
   1.6+. If the project pulls an older compose-icons artifact, the
   back-icon imports will need to fall back to `Icons.Default.Close`.
- HN rate-limits harshly. The submit-hn.py docstring warns: do NOT
   re-run within 60 minutes of a submission.

## Status of the bet (recap from idea #22 risk register)

- Idea #19 micro-SaaS for GraphQL on Android.
- LLM-disruption risk: **LOW**. A GraphQL client has high ongoing-
  value (every query you save, every endpoint you add is locked
  into the user's workflow). Static-utility SaaS would be at risk;
  this isn't static.
- 30-day revenue target post-launch: $50–$200 from early adopters.
- 90-day target: $500–$1k MRR if launch hits.
- Ceiling on Android-only: $500–$5k MRR. iOS-port upgrade path
  triggers at $1k MRR ($99/yr Apple Developer is trivial).