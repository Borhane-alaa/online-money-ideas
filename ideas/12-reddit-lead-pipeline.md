---
title: Reddit lead-pipeline (intent scraping)
slug: reddit-lead-pipeline
status: dropped
added: 2026-09-05
effort: 3
skill: 3
ceiling: 3
risk: 4
verdict: Drop. ToS gray, fragile, and the AI-shaped reply arms-race makes it toxic.
tags: [automation-services]
---

## Premise

Scrape Reddit / HN / niche forums for posts where users explicitly ask for
what you sell ("looking for a CRM for my yoga studio", "anyone recommend an
email tool for course creators"). Auto-DM them with a pitch.

## Why it's dropped

- Reddit TOS explicitly prohibits automated scraping + unsolicited DM.
  Reddit API v2 pricing in 2023+ makes this uneconomic at small scale.
- Users actively detect and flame AI replies; karma destruction on the
  account is fast.
- "Cold pitch" reply becomes spam once you scale — every subreddit flags you.
- Fragile: scraping pipelines break weekly as Reddit changes the site.

The whole "harvest leads from forums" category was already a saturated
shady pattern in 2018, then LLMs made it 10x more visible (and 10x more
detectable). Burn the idea.

## Verdict

Dropped. If you want forum-based marketing, do it the boring way: post
useful answers with a profile link. Don't automate the reply.