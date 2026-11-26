# 2026-11-26 · analytics run (parallel duplicate — no site changes)

## Why this report exists
Two sessions ran the analytics task on 2026-11-26. This session (claude.ai/code/session_017ECXT4qyGvTBikR3zTQBiQ)
was fired at 15:42 UTC, is marked "failed: usage limit" in the task list, but kept running. A second session
(session_017ECXT2CXCfBNiG1Xc5keeu) pushed `f0860cb` at 15:44 UTC (A1/B1 titles, descriptions, H1s, A1 links,
sitemap, deploy probe). When this session tried to push its own A1/B1 title changes, the push was rejected
because `f0860cb` was already on `main`. To avoid two runs rewriting the same titles within minutes (which would
make the 21-day measurement meaningless), this session **discarded its page edits and pushed nothing to the site**.
The changelog entry for `f0860cb` belongs to the other run; this file only adds this session's data analysis and
proposals. No changelog entry was added here, to avoid an append conflict with the other run.

## Data (Windsor.ai; trial = last 30 days only)
Previous 28 days (2026-09-30 – 2026-10-27) are NOT available: Windsor refuses ranges older than 30 days
("your trial includes the last 30 days"). Comparisons below are therefore: last 14 days vs the 14 days
before, and the full 28 days vs the playbook baseline (28 days to 2026-11-14, which overlaps this window).

Search Console, 2026-10-28 – 2026-11-24 (data lag; 11-25 not yet available):
- 28 days: 58 clicks, 557 impressions, CTR 10.4 %, avg position 7.5 (impression-weighted from daily rows).
  Baseline: 19 clicks, 289 impressions.
- 10-28 – 11-10: 17 clicks, 160 impr, pos 9.8 · 11-11 – 11-24: 41 clicks, 397 impr, pos 6.6.
- Weekly: 7/69 · 10/91 · 23/162 · 18/235 (clicks/impressions). The step up starts around 11-13 to 11-15,
  i.e. partly before the 11-15/11-16 agent changes. No single edit can be credited.
- Pages, 28 days (clicks / impressions / position / CTR): home 18/176/5.3/10 % · B2 13/95/8.0/14 % ·
  C1 12/66/4.7/18 % · A2 6/40/8.8/15 % · B1 6/131/9.7/4.6 % · start 2/32/11.1/6 % · A1 1/41/9.0/2.4 % ·
  articles guide 0/23/6.9 · tips 0/11/10.7 · B1 topic page 0/1/5.
- Biggest movers (first vs last 14 days): B2 impressions 14 → 81 (pos 12.5 → 7.3, clicks 2 → 11);
  B1 35 → 96 (pos 16.2 → 7.3); A1 10 → 31 (pos 16.8 → 6.5); articles guide 4 → 19. start.html slipped
  (pos 4.6 → 14.0 on 10 → 22 impressions).
- Query rows cover only ~41 of 557 impressions (Google hides rare queries). Visible queries at positions
  5–20: "telc b1 vocabulary list" 8 impr (daily 5–10 recently), "telc b2 vocabulary list" 6 impr pos 9.3,
  "telc vocabulary list" 4 impr pos 6.8 (home), "telc a1 vocabulary list"/"word list" 2+2 at ~6–7,
  "telc a2 vocabulary list" 1 at 7, "telc trainer" 1 at 9 (start.html), "wortschatz c1 deutsch liste pdf telc" 1 at 9.

GA4 sessions, 2026-10-29 – 2026-11-25 (28 days): 339 total (baseline 205).
- direct 117 (base 83) · reddit.com 84 (53) · google organic 83 (30) · bing organic 25 (16) · other 28
  (ecosia 10, duckduckgo 4, chatgpt 3, telegram 3, yahoo 3, cn.bing 2, gemini 1, t.co 1, not set 1).
- First 14 days → last 14 days: google 19 → 64, reddit 35 → 49, direct 56 → 61, bing 15 → 10.
  Engagement rate: reddit 57 % → 61 %, google 74 % → 44 % (more list-page visitors who leave after scanning).
- Page views: / 349, B1 list 42, A2 41, B2 27, C1 19, A1 19, start 9, B1 topic page 2, tips 2, articles 1.

## Judging earlier changes
- Articles guide (title/description changed 2026-11-16): impressions rose to 19 at pos ~6.6 in the last 14 days,
  0 clicks. Too early; judge on/after 2026-12-07 as planned.
- B1 topic page (new 2026-11-16): 1 impression, 2 GA4 sessions in 10 days. Not indexed for its target yet.
- Technical changes 2026-11-15/16: the organic rise overlaps them, but it began ~11-13 and is spread over all
  list pages incl. ones with no specific change (B2, C1). Most likely recrawl/normal growth; not attributable.
- Reddit: steady daily referrals, no spike → no sign yet that the 2026-11-25 r/German draft was posted.

## Monthly review: German / Turkish (and other non-English) queries
Visible rows, 2026-10-28 – 2026-11-24: "telc b1 wortschatz" 2 impr pos 53.5 · "telc b2 wortschatz" 2 impr pos 4.5
(1 click) · "telc b2 wortliste" 1 at 26 · "wortschatz c1 deutsch liste pdf telc" 1 at 9 · "telc a1 kelime listesi"
1 at 52 · Russian "слова на немецком b1" 1 at 1. Country rows (only 37 impressions attributed): Germany 24, of which
B1 list 13 at avg pos 27.8. Volume is tiny, so the data neither proves nor rules out demand.
Recommendation: stay English-only for now (matches the owner's decision). Low-risk step inside the rules: use the
German exam terms "Wortschatz"/"Wortliste" in English titles/intro text of list pages (B2 already ranks 4.5 for
"telc b2 wortschatz" with the word only in the table). Revisit at the next monthly review with 2 months of data.

## Proposals prepared but NOT applied (for the next analytics run, after 2026-12-17 for A1/B1 titles)
1. Print stylesheet on the five level pages (so "Print → Save as PDF" gives a clean black-on-white list;
   tested in headless Chromium: B1 prints as 81 A4 pages, header/search/buttons hidden). One CSS line before
   `</style>`: `@media print{body{background:#fff;color:#000;padding-bottom:0}header.top,.sticky-play,.cta,#q,#count,.letters,footer,.cards{display:none!important}p,li,td,th,h1,h2,h3,.note,.crumbs,.letter-h{color:#000!important}a{color:#000}.art{-webkit-print-color-adjust:exact;print-color-adjust:exact}}`
   Also hide the "Other levels" h2 in print.
2. FAQ (visible + FAQPage JSON-LD) on level pages: "Can I download the B1 word list as a PDF?" → "There is no separate
   PDF file. Open this page, use your browser's Print option and choose "Save as PDF" …" (only after 1. is live), and on
   B1: "Is this the official telc B1 word list?" (same answer as the existing A1 FAQ).
3. Alternative titles considered for A1/B1 (if f0860cb's versions do not lift CTR by 2026-12-17):
   `TELC B1 Vocabulary List (Wortschatz): 2,098 Words + English` / same pattern for A1.

## Backlog ideas for the content agent (not written into BACKLOG.md here to avoid conflicts)
- "PDF" intent ("wortschatz … liste pdf telc"): printable list (proposal 1) rather than a new page.
- start.html is losing position for generic "telc vocabulary" queries where the home page also ranks; consider
  differentiating start.html (overview of levels/word counts) rather than a second "trainer" page.

## Verification
No site change from this session, so no deploy probe and no live fetch. The other run's `f0860cb` set the probe
`2026-11-26T15:43:56Z deploy probe: analytics run`; its live verification is that run's responsibility.
