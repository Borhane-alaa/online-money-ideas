# 2026-09-05 — Wave 1: HN-curated research fetched

## What I did

- Pulled 6 HN search queries (`>50` hits per query) via the Algolia API.
- Pulled the comment trees of 4 canonical revenue-disclosure threads
  (25372464, 25434753, 15593589, 35567822 — 1,164 total).
- Extracted named, revenue-attached product mentions from the comments:
  33mail ($8k/mo after 10y), Buttondown (Buttondown.email, $2k MRR after 2.5y),
  ScrapingFish ($2k/mo after 5–6 mo), jpdb.io ($1996/mo Patreon after 2y),
  Pirsch Analytics ($4k MRR after 1.5y), HTTP Toolkit ($2k+/mo), PixelPeeper
  ($2k/mo after 1–2 mo), PlaylistAI ($2.5k MRR after 2 wk), Proxyman iOS
  ($2k/mo MRR), get-notes.com ($2k/mo from ads), ExtensionPay, Kpopping,
  and ~50 more.
- Pulled 4 high-signal write-ups (BookmarkOS, Campfire Labs "$5k side
  project," Pragmatic Engineer's "I replaced a $120/yr micro-SaaS in 20
  minutes," OpenSaaS.sh "$550 MRR GPT wrapper").
- Wrote 8 new idea files (#18–25), updating the master table.

## New ideas added

| # | slug | status | source signal |
|---|------|--------|---------------|
| 18 | disposable-utility-saas | validate-next | 33mail (HN 25434753) |
| 19 | mobile-dev-utility-app-store | validate-next | Proxyman iOS, PlaylistAI (HN 35567822) |
| 20 | privacy-first-analytics | validate-next | Pirsch (HN 35567822), Plausible/Fathom public data |
| 21 | micro-saas-creator-niche | validate-next | PixelPeeper (HN 35567822) |
| 22 | llm-replacing-micro-saas | risk-register | Pragmatic Engineer Feb 2026 post |
| 23 | niche-content-site-subscription | validate-next | jpdb, get-notes, Kpopping, DamnInteresting (HN 35567822) |
| 24 | extension-monetization-infra | validate-next | ExtensionPay (HN 35567822) |
| 25 | acquire-micro-saqs-operator | back-burner | microacquire.com mentions (HN 35567822) |

## Most important finding (counter-signal to the whole vault)

**The Pragmatic Engineer (Feb 2026) replaced a $120/yr paying SaaS
(Shoutout.io) in 20 minutes using Codex.** This is direct evidence that
**static-utility micro-SaaS are structurally at risk of LLM replacement.**

The implication is *not* "give up on micro-SaaS" — it's "score every
micro-SaaS idea on an ongoing-value axis before validating." I created
`22-llm-replacing-micro-saas.md` as a meta risk-register entry, and
referenced it from the static-utility ideas (especially #18).

What this means for my shortlist:
- Micro-SaaS without ongoing value (testimonials, static badges, basic
  formatters): **drop**.
- Micro-SaaS with ongoing value (analytics, alerts, dashboards,
  compliance): **still valid**.
- Consumer micro-SaaS (Proxyman, PixelPeeper, PlaylistAI): **still
  valid** — the customer doesn't have the LLM-coding skill to rebuild.

## What I did NOT do (and why)

- IndieHackers JS-rendered site blocked clean extraction. Marked wave
  dead-end for now. Future wave can try `indiehackers.com/products.json`
  which returns a 200 but seems to be HTML too.
- MicroConf talk transcripts: didn't fetch — would need a transcript
  database. Move to a future wave.
- ProductHunt API: requires auth. Skipped for now.
- Algora / Gitcoin bounties: not high-signal for "make money online"
  — they're for OSS maintainers specifically. Skipped.

## Decisions made today

- **#22 is a risk register, not a business.** Filed separately so I can
  refer to it from other idea files without polluting the master table.
- **#25 (acquire existing) stays back-burner.** Capital + sourcing is
  hard, and LLM-disruption risk hits bought assets hard.
- **#19 (mobile dev utility on App Store) is the most underestimated
  lane.** The 30% App Store cut is real but the discoverability
  problem is bounded. Bumped.

## Next research waves (queue)

1. Wave 2: pull Pirate metrics / arvid-kahl "Zero to Sold" book notes,
   Tyler Tringas MicroConf talks for the canonical micro-SaaS playbook.
2. Wave 3: actually fetch the IndieHackers /product/<slug> HTML pages
   directly (curl them as text, ~50 fetches in parallel) for revenue
   disclosures.
3. Wave 4: Algora / OSS-sponsor revenue rankings.
4. Wave 5: Bountied dev tooling (actually skip — niche).

## Next action

After this wave lands, pick ONE idea to deep-dive for a 14-day MVP test.
The strongest candidates after wave 1:
- #19 (mobile dev utility on App Store)
- #20 (privacy-first analytics, with a niche wedge)
- #21 (micro-SaaS for one creator niche)