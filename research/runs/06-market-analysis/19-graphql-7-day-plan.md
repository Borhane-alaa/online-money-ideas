# Operational Plan: #19 GraphQL Client for Android — 7-Day Build

**Date:** 2026-09-05
**Decision locked:** #19 mobile dev utility + **GraphQL** wedge + **Android-only**
(publisher account already paid).
**Working name candidates:** "GraphQL Pocket", "QuokkaQL",
"GraphQL Console for Android". (Pick one before Day 1 end.)

---

## 0. Pre-build verification

This is the bet, not the bet's bet. Run these checks before Day 1:

- [ ] Verify Play Console account is in good standing (open
      https://play.google.com/console, confirm you can create a new
      app).
- [ ] Install Android Studio (latest stable). Verify a hello-world
      APK builds to your connected device or emulator.
- [ ] Pick a name. **Recommendations in priority order:**
      1. **"QuokkaQL — GraphQL Client"** (cute, memorable, not yet
         taken; "quokka" is the brand of dev tools e.g. quokkalabs).
      2. **"GraphQL Pocket"** (literal, SEO-friendly, slightly boring).
      3. **"Apollo Console for Android"** (free-rider on Apollo's brand;
         risky for trademark — **don't pick this**).
      Avoid any name that uses "Proxyman" or "Insomnia" or "Postman"
      (all are existing trademarks).
- [ ] Reserve the matching `com.<your-prefix>.<app-name>` package
      name. **Don't** reverse-domain on `com.graphql.*` (Play Console
      warns on namespace squatting). Use your own domain.

---

## 1. The MVP — exact feature list (do NOT add to this in week 1)

The competitor (`info.camposha.graphql_viewer`) ships this exact
list. To be a credible alternative at v1, you need all of it. Don't
add anything beyond this list until week 4.

### MVP scope (hard cut)

- [ ] **Endpoint management**
  - Add / edit / delete GraphQL endpoints.
  - Each endpoint has: URL, name, optional default headers.
  - Persist locally (DataStore preferences, no account needed).
- [ ] **Query editor**
  - Monospace text input (use `BasicTextField` + monospace font).
  - JSON variable editor below the query.
  - Tab key inserts spaces, not focus changes.
  - Syntax-error indicator if query is non-empty and unparseable
    (don't build a real parser; just brace-count).
- [ ] **Headers editor**
  - Per-endpoint + per-request headers.
  - Authorization header field at the top of the request screen.
- [ ] **Response viewer**
  - JSON tree view (use a library, don't roll your own).
  - Status code + response time.
  - Copy response as JSON.
- [ ] **Saved queries**
  - Per-endpoint: name + query + variables → run with one tap.
  - Persist locally.
- [ ] **Query history**
  - Last 50 queries auto-saved (per endpoint).
  - Tap to re-load into editor.
- [ ] **Settings screen**
  - Theme (system / light / dark).
  - Default timeout.
  - "Clear all data" button.

### Out of MVP (DO NOT build in week 1)

- ❌ Subscriptions / WebSockets (GraphQL subscriptions).
- ❌ Code generation / schema → Kotlin.
- ❌ Cloud sync / accounts.
- ❌ Export / import endpoints as JSON.
- ❌ Postman collection import.
- ❌ AI query generation.
- ❌ Plugins / themes.
- ❌ Proxyman-style HTTPS interception (different product; reserved
  for v2).

### Library choices (kotlin only)

| need | library | why |
|------|---------|-----|
| HTTP client | OkHttp 4.x | standard, easy coroutine integration |
| JSON | kotlinx.serialization | first-party Kotlin, no kapt needed |
| JSON tree view | roll-your-own (3 files, ~300 LOC) OR copy from open-source `JsonTreeView` | library is small enough |
| Navigation | Jetpack Compose Navigation | standard |
| Persistence | DataStore Preferences (not Room — over-engineering for week 1) | typed |
| Build | Gradle KTS | standard |

---

## 2. Day-by-day schedule

This is built around your 7-day window. Day 7 = production rollout
to Play Store. Don't ship before Day 7 — the Play Store review
cycle takes 3–7 days, so anything you submit earlier is just
waiting in queue.

### Day 1 — Scaffold + endpoint mgmt

**Goal:** App opens, shows an empty endpoints list, can add an endpoint.

- [ ] Create Android Studio project (Kotlin, Compose, min SDK 26).
- [ ] Set package name from your reservation.
- [ ] Add dependencies: OkHttp, kotlinx.serialization.
- [ ] Implement endpoints screen (list + FAB to add).
- [ ] Implement endpoint form (URL, name, headers).
- [ ] Persist endpoints with DataStore.
- [ ] Wire up navigation.
- [ ] **End-of-day check:** app runs on emulator, add → save → reload
      works.

### Day 2 — Query editor + run

**Goal:** From an endpoint screen, tap into a query editor, type a
query, run it, see the response.

- [ ] Add query screen (endpoint detail → query editor).
- [ ] Editor: BasicTextField with monospace font, brace counter.
- [ ] Run button uses OkHttp POST against `${endpoint.url}`,
      body = `{"query": ..., "variables": ...}`, headers = endpoint
      headers + Authorization if present.
- [ ] Response viewer: status code, time, JSON tree.
- [ ] **End-of-day check:** runs a real GraphQL query against
      countries.trevorblades.com or similar public endpoint, shows
      response.

### Day 3 — Saved queries + history

**Goal:** Power-user features so the app is actually useful.

- [ ] Save current query (name + query + variables) to endpoint.
- [ ] Show saved-queries list under the query editor.
- [ ] Auto-add to query history (last 50) on each run.
- [ ] Tap history entry to re-load.
- [ ] **End-of-day check:** 3 saved queries, history of 5 runs,
      reload from history works.

### Day 4 — Polish + settings + paywall

**Goal:** App is ready for paid users.

- [ ] Settings screen: theme, timeout, clear-all-data.
- [ ] Add Play Billing Library 7 dependency.
- [ ] Implement subscription paywall:
  - **Free:** up to 2 endpoints, 10 saved queries, 7-day history.
  - **Pro:** unlimited endpoints, unlimited saved, unlimited history,
    dark theme customization.
- [ ] Pricing:
  - **Monthly:** $2.99/mo
  - **Yearly:** $19.99/yr (saves 44%)
  - **Lifetime:** $39.99
  - 7-day free trial (auto-converts to monthly, can cancel).
- [ ] **End-of-day check:** free user hits endpoint limit, upgrade
      flow opens Play purchase sheet.

### Day 5 — Play Console submission (internal test first)

**Goal:** APK on internal testing track, ready to invite 10 friends.

- [ ] Generate signed release APK (jks keystore).
- [ ] Upload to Play Console → Internal testing track.
- [ ] Fill in store listing (see section 5).
- [ ] Create internal-testing email list (your 10 dev friends).
- [ ] Roll out to internal testers.
- [ ] **End-of-day check:** testers can install via internal-test
  Play URL.

### Day 6 — Fix top 3 bugs from testers + production submission

**Goal:** Ready for production.

- [ ] Read tester feedback. Fix the top 3 bugs.
- [ ] Push new build to internal track.
- [ ] Submit for production review: Play Console → Production →
      Release.
- [ ] Fill in release notes, content rating questionnaire (IARC),
      data safety form.
- [ ] **End-of-day check:** status "In review" or "Approved" in Play
  Console.

### Day 7 — Launch

**Goal:** Live on Play Store + soft-launched on community channels.

- [ ] Confirm "Published" status.
- [ ] Post HN Show HN (text in section 7 below).
- [ ] Post r/androiddev (cross-post from HN, follow subreddit rules).
- [ ] Post r/GraphQL.
- [ ] DM 5 niche influencers / dev-tooling newsletter writers.
- [ ] Update README on any of your GitHub projects to mention the
      app (cross-prom if appropriate).

---

## 3. File tree (target)

```
quokkaql/
├── app/
│   ├── build.gradle.kts            # module config
│   ├── proguard-rules.pro
│   └── src/main/
│       ├── AndroidManifest.xml
│       ├── kotlin/com/yourname/quokkaql/
│       │   ├── MainActivity.kt
│       │   ├── QuokkaQLApp.kt           # Application class
│       │   ├── ui/
│       │   │   ├── theme/                # Compose theme + colors
│       │   │   ├── nav/                  # NavHost
│       │   │   ├── endpoints/            # EndpointsScreen + VM
│       │   │   ├── endpoint/             # EndpointDetailScreen + VM
│       │   │   ├── query/                # QueryEditor + response viewer
│       │   │   ├── settings/
│       │   │   └── paywall/              # SubscriptionScreen + IAP
│       │   ├── data/
│       │   │   ├── endpoint/             # Endpoint data class + repo
│       │   │   ├── query/                # SavedQuery + history
│       │   │   └── prefs/                # DataStore wrappers
│       │   ├── net/
│       │   │   ├── GraphQLClient.kt      # OkHttp wrapper
│       │   │   └── GraphQLRequest.kt     # request DTO
│       │   └── util/
│       │       ├── json/                 # Brace counter, formatter
│       │       └── billing/              # Play Billing wrapper
│       └── res/
│           ├── values/
│           │   ├── strings.xml
│           │   ├── colors.xml
│           │   └── themes.xml
│           ├── drawable/                 # ic_launcher, etc
│           ├── mipmap-anydpi-v26/        # adaptive icons
│           └── xml/                      # backup_rules, data_extraction
├── build.gradle.kts
├── settings.gradle.kts
├── gradle.properties
└── keystore/                            # your release.jks (gitignored)
```

Total Kotlin LOC target for week 1: **~2,000–3,000**. Mostly UI +
OkHttp calls. Don't over-engineer.

---

## 4. Pricing decision (final)

Locked:

| tier | price | includes |
|------|------:|----------|
| Free | $0 | 2 endpoints, 10 saved queries, 7-day history |
| **Monthly** | **$2.99/mo** | unlimited everything |
| **Yearly** | **$19.99/yr** | unlimited everything, ~44% savings |
| **Lifetime** | **$39.99** | one-time, unlimited forever |
| Trial | 7 days | full Pro access, auto-converts to monthly |

**Rationale:**
- Monthly $2.99 is the Google Play sweet spot for utility (matches
  the few paid dev utilities in the scrapes — $4.09 API Tester Pro,
  $7.99 DC Webhook Pro).
- Yearly 44% discount nudges annual conversion.
- Lifetime exists for the "I use this daily, take my $40" segment.
- 7-day trial reduces purchase friction. Conversion rate of trial-
  to-paid for utility apps is typically 30–60%.

If free-tier usage proves high and conversion proves low, raise the
price in month 3 (after you have telemetry).

---

## 5. Play Store listing (draft)

### Short description (80 chars)

> GraphQL client in your pocket. Endpoints, headers, schema, saved
> queries.

### Full description (4000 chars)

```
QuokkaQL is a focused GraphQL playground for Android.

Built for the developer who is already using GraphQL on the desktop
and wants the same workflow on a phone — testing a resolver during
a deploy, debugging an API from a customer call, or checking a
schema from a meeting.

Every feature you'd expect, no account needed:

• Multi-endpoint workspace — manage Production, Staging, and
  local dev in one tap. Each endpoint has its own URL, custom
  headers, and cached schema.

• Real query editor — monospace, tab-to-indent, JSON variable
  validation. The editor flags malformed requests before you
  hit send.

• Custom headers per endpoint — Authorization, API keys, or
  anything else. Authenticated APIs work without copy-pasting
  tokens.

• Schema browser — introspection query loads the complete
  schema. Browse Queries, Mutations, and Types. Tap a field to
  insert a ready-to-run stub.

• Saved queries — name and store your favorite queries, run
  them again with two taps.

• Query history — your last 50 queries, automatically saved
  per endpoint.

• Themes — light, dark, or follow system.

Free tier: 2 endpoints, 10 saved queries, 7-day history.
Pro tier: unlimited everything, 7-day free trial, $2.99/mo,
$19.99/yr, or $39.99 lifetime.
```

### App icon

- Adaptive icon, 432x432 px source.
- Use a quokka silhouette on a flat background, or a G-letter mark.
- A ICON SHOULD LOOK DIFFERENT FROM THE COMPETITOR'S — Clement's
  app uses blue + white; pick a different palette (teal? orange?).

### Screenshots (8 required, 4–6 recommended)

1. Endpoints screen (empty state + 2 endpoints).
2. Query editor (typing a query).
3. Response viewer (JSON tree).
4. Schema browser.
5. Saved queries.
6. Paywall.
7. Settings (dark theme).
8. Icon showcase (just the icon on a phone).

Use a Pixel 6 frame. Light background, ~80% app, 20% marketing text
above. Be honest — don't fake testimonials on the screenshot.

### Content rating

- IARC questionnaire: "Utilities > Developer tools".
- No violence, no adult, no gambling, no user-generated content.
- Should auto-rate **Everyone**.

### Data safety

- "No data shared with third parties" — true (no analytics SDKs in
  week 1).
- "No data collected" — true (local-only persistence).
- This is a competitive advantage. Plausible's data privacy
  positioning is partly why it wins; replicate it.

---

## 6. Pre-launch tester list (Day 5 target)

Pick 10 developer friends / Twitter mutuals. Targets:

- 3 Android developers (will catch UI / lifecycle bugs).
- 3 backend developers who use GraphQL (will catch workflow bugs).
- 2 indie hackers / solo SaaS builders (the target customer).
- 2 GraphQL power users (will catch schema edge cases).

Email template (use the email field of your Play Console internal-
testing track):

```
Subject: Test my new Android GraphQL client?

Hi <name>,

I built a focused GraphQL client for Android over the past 5 days
and I'd love your feedback before the public launch.

Quick install:
  <internal-testing-URL>

What I'd love:
  - Try a real workflow against one of your endpoints
  - Anything that crashes / feels broken
  - Anything you'd expect a tool like this to have

If you can spare 10 minutes, just install and use it for whatever
you'd use a GraphQL client for today.

Thanks!
```

---

## 7. Launch post text (Day 7)

### HN Show HN

**Title:** Show HN: QuokkaQL – A GraphQL client for Android

**Body:**

```
Hey HN,

I built QuokkaQL, a focused GraphQL client for Android, over the
past 7 days. It's free with a $2.99/mo or $19.99/yr Pro tier.

Why this, why now: I went looking for a decent GraphQL client on
Android before building it. Found exactly one — 50+ installs, no
paid tier, no active development. There are ~25 apps in the
"REST client" category but basically zero in the GraphQL niche.

So I built one. What's in v1:

- Multi-endpoint workspace (URL + headers per endpoint)
- Real query editor (monospace, JSON variables)
- Schema introspection browser
- Saved queries
- 50-deep query history per endpoint
- Subscription paywall (Play Billing)

What's not in v1 (intentionally): subscriptions/websockets, AI
query generation, cloud sync, Postman imports.

Tech: native Kotlin + Compose, OkHttp for HTTP, kotlinx.serialization
for JSON, Play Billing Library 7 for IAP. ~2,500 LOC.

Distribution problem is bounded: Play Store SEO + this post. I
priced it where the few paid Android dev utilities sit ($2.99–$9.99
range).

Happy to answer questions about the build, the pricing decision,
or the launch.
```

### r/androiddev (cross-post, follow subreddit rules — read them
first)

**Title:** I built an Android GraphQL client because there wasn't one.
Here's what shipped in 7 days.

**Body:** A trimmed version of the HN post, with the focus on
"lessons from shipping a Play Store app in a week" rather than the
product itself. Include a screenshot of the query editor.

### r/GraphQL

**Title:** Built an Android GraphQL client — what's missing in the
mobile dev experience?

**Body:** A question-framed post. Ask what pain points people have
with mobile GraphQL tooling. Useful both for marketing and for
shaping v2.

---

## 8. What I am NOT doing in this plan

- ❌ iOS port — wait until Android revenue compounds past $1k MRR.
- ❌ Cloud sync / accounts — adds a backend you have to operate,
  kills the "no account needed" differentiator.
- ❌ AI features — adds cost, doesn't address the core wedge.
- ❌ Custom keyboard / IME integration — over-engineering for v1.
- ❌ Tablet-optimized layout — defer to v2 unless you own a tablet.

---

## 9. Risk register (carry-forward from idea #22)

The LLM-disruption risk register applies here, with a positive twist:
**a GraphQL client has high ongoing-value** (each query you run,
each endpoint you save, each saved-query you write is locked into
the user's workflow). The LLM-replacement risk for idea #19 is **1/5**
(dev utility = ongoing value). Confirmed.

The bigger risks are:

- **Android-only ceiling.** Realistic solo MRR is $500–$5k. Plan
  for the iOS upgrade path starting at $1k MRR.
- **Discoverability in a low-volume niche.** "GraphQL client" is a
  low-volume Play Store search term. The launch post carries most
  of the GTM.
- **Refund rate on the 7-day trial.** Watch Play Console for refund
  rate; if >10%, the trial-to-paid conversion is broken.

---

## 10. Decision points for the user (post-MVP)

After launch, weekly check-ins with these questions:

1. Are installs > 100/day? (If yes, scale GTM. If no, find a
   different subreddit.)
2. Trial-to-paid conversion > 30%? (If no, fix the paywall or
   shorten the trial.)
3. Are testers asking for features you don't have on the MVP
   list? (Add to v2 if 3+ users ask.)
4. Is there any signal that iOS users want this? (If yes, plan
   the iOS port — buy Apple Developer at $99/yr.)

## Sources

- Play Store search data: 5 GraphQL-related keywords scraped
  2026-09-05. 66 unique apps across the 5 searches; **only 1**
  is a dedicated GraphQL client (`info.camposha.graphql_viewer`,
  50+ installs, free, no IAP, last updated May 2026).
- Competitor detail page pulled and analyzed for description +
  positioning.
- Pricing benchmarked against 4 paid Android dev-utility apps
  scraped earlier this session (range $4.09–$164.99).