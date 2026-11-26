# 2026-11-26 · analytics run (first analytics run; also the November monthly review)

## Note: duplicate run
A second session ran the same scheduled task at the same time (report
`2026-11-26-analytics-parallel-run.md`). It saw `f0860cb` on main, discarded its own page edits
and pushed only a data report. Its numbers match this report. It reads the step-up as starting
11-13 to 11-15 (partly before the agent changes); that is the more cautious reading. The owner may
want to check why the task fired twice (it was marked "failed: usage limit" but kept running).

## Data access and limits
- Windsor.ai connectors worked (Search Console `sc-domain:telcwords.com`, GA4 `531222453`).
- The Windsor trial only returns the last 30 days. A request from 2026-09-29 was refused, so the
  **previous 28-day period is not available**. Instead: last 28 days in total, split into two
  14-day halves, plus comparison with the PLAYBOOK §5 baseline.
- Windows: Search Console 2026-10-28 – 2026-11-24 (data lags ~2 days); GA4 2026-10-29 – 2026-11-25.
  Halves: H1 = 2026-10-28 – 11-10, H2 = 2026-11-11 – 11-24.
- Query-level rows cover only 18 queries (~3 of 58 clicks); Google hides most low-volume queries.
  Page-level numbers are complete.
- Baseline note: PLAYBOOK says 19 clicks / 289 impressions for the 28 days to 2026-11-14, but the
  data pulled today gives 25 clicks / 214 impressions for just 2026-10-28 – 11-14 (18 days). GSC
  figures were probably still incomplete when the baseline was taken; treat baseline clicks as a
  lower bound.

## Key numbers (computed in Python from the pulled rows)
| | Baseline (28 d to 11-14) | Last 28 days | H1 (14 d) | H2 (14 d) |
|---|---|---|---|---|
| GA4 sessions, all | 205 | 339 | 142 | 189 |
| direct | 83 | 118 | 59 | 54 |
| reddit.com referral | 53 | 84 | 34 | 49 |
| google organic | 30 | 84 | 19 | 63 |
| bing organic | 16 | 25 | 15 | 10 |
| GSC clicks | 19 | 58 | 17 | 41 |
| GSC impressions | 289 | 557 | 160 | 397 |
| GSC avg position | – | 7.5 | 9.8 | 6.6 |
| GSC CTR | – | 10.4 % | 10.6 % | 10.3 % |

Step change on 2026-11-15: impressions per day 11.9 (10-28 – 11-14) → 34.3 (11-15 – 11-24);
average position 8.9 → 6.7; Google organic sessions 31 in 18 days → 53 in 11 days. The jump
begins the day og-image tags and new sitemap lastmod values went live (11-15) and the day before
the technical-seo/content work (11-16). The timing is consistent with recrawl after those changes,
but a 10-day window on a young site cannot rule out ordinary indexing growth. Not claimed as cause.

Pages, Search Console, H1 → H2 (impressions / position / clicks):
- `/` 69 / 6.5 / 7 → 107 / 4.5 / 11
- B1 list 35 / 16.2 / 1 → 96 / 7.3 / 5 (CTR 5.2 %, lowest of the big pages)
- B2 list 14 / 12.5 / 2 → 81 / 7.3 / 11 (CTR 13.6 %)
- C1 list 21 / 4.8 / 4 → 45 / 4.7 / 8
- A1 list 10 / 16.8 / 0 → 31 / 6.5 / 1 (CTR 3.2 %)
- A2 list 20 / 10.9 / 2 → 20 / 6.8 / 4
- start.html 10 / 4.6 / 1 → 22 / 14.0 / 1 (losing position; likely overlaps with `/` for generic queries)
- articles guide 4 / 8.0 / 0 → 19 / 6.6 / 0
- tips guide 6 / 7.5 / 0 → 5 / 14.6 / 0
- B1 topic page: 1 impression (2026-11-19, pos 5); not yet meaningfully indexed.

Queries at positions 5–20 with impressions: "telc b1 vocabulary list" (B1 list, 8 impr, pos 17.5,
1 click), "telc b2 vocabulary list" (B2, 6, 9.3), "telc vocabulary list" (`/`, 4, 6.75),
"telc a1 vocabulary list" (A1, 2, 7.5), "telc a1 word list" (A1 pos 7, `/` pos 4),
"wortschatz c1 deutsch liste pdf telc" (C1, 1, 9), "telc trainer" (start.html, 1, 9).

GA4 landing pages (28 d): `/` 237 sessions (direct 106, Reddit 76, organic 51); organic entries on
level pages: B2 17, A2 15, B1 14, C1 12, A1 4; 13 organic sessions with landing page "(not set)"
and 0 engagement (probably sessions without a page_view; ignore). New/small referrers: chatgpt.com 3
(all engaged), gemini 1, yahoo 3, cn.bing.com 2, web.telegram.org 3 (0 engaged), t.co 1.
Reddit: 1–8 sessions every day, no spike after 2026-11-25; no sign yet that the drafted r/German
post (articles guide) went out (no social landings on that guide).

## Changes made (commit `f0860cb`, edits by an Opus subagent, reviewed by the main session)
Only the two big list pages with weak CTR at positions 6–8 (B1, A1). A2/B2/C1 left unchanged as a
control group (their CTR is 13–20 %). Exact old/new text is in CHANGELOG.
- `telc-b1-vocabulary.html`, `telc-a1-vocabulary.html`: title, meta description, og/twitter
  title+description, H1 now lead with the searched phrase "TELC B1/A1 Vocabulary List".
- A1 list: contextual links to the articles guide and to the A2 list.
- sitemap lastmod 2026-11-26 for those two URLs; deploy-check.txt.
- Not changed: articles guide (title changed 2026-11-16, 21-day rule, judge on/after 2026-12-07);
  index.html, .htaccess, word data untouched (diff checked).
Self-checks: one title/description/canonical/H1 each, descriptions 149 and 145 chars, all JSON-LD
parses, html.parser clean, all root-relative links resolve, sitemap parses, no `<tr>` lines in diff.

## Live verification (web fetch, 2026-11-26 ~15:50 UTC)
- deploy-check.txt: `2026-11-26T15:43:56Z deploy probe: analytics run` ✔
- First fetch of the two pages and of sitemap.xml returned an **old copy** (sitemap with all lastmod
  2026-10-24, i.e. the pre-11-15 version, 9 URLs). A second fetch with a different query string
  returned the current versions: B1 and A1 new title/description/H1 ✔, A1 new links ✔, tables render ✔,
  sitemap 10 URLs with 2026-11-26 lastmod ✔, topic page 200 ✔, start.html links to topic page ✔.
  So some fetch path (tool or edge cache) can serve stale copies; always use a fresh, unique query
  string and re-fetch before concluding a deploy failed.

## Monthly review (November)
- Against baseline: sessions +65 % (205 → 339), Google organic ×2.8 (30 → 84), Reddit +58 %,
  GSC impressions ×1.9, clicks ×3 (baseline clicks probably understated, see above).
- Earlier changes: 11-15/16 batch (og tags, sitemap, technical-seo, content) coincides with the
  impression step-up; plausible, not proven. Articles guide retitle: 4 → 19 impressions, still
  0 clicks; too early (judge 2026-12-07). B1 topic page: not ranking yet.
- German/Turkish/other-language queries (28 d, visible rows only): "telc b2 wortschatz" B2 list
  pos 4.5, 2 impr, 1 click; "telc b2 wortliste" pos 26; "telc b1 wortschatz" pos 53.5, 2 impr;
  "wortschatz c1 deutsch liste pdf telc" pos 9; "telc a1 kelime listesi" pos 52; two Russian
  queries at pos 1. By country: Germany 272 of 557 impressions (49 %) and 41 of 58 clicks (71 %);
  Türkiye 10 impressions, pos 14.1, 0 clicks.
- Recommendation for the owner: stay English-only (volume is tiny and the English pages already
  catch some German queries, e.g. B2 at 4.5). Optional low-risk step needing his OK: one English
  sentence per level page naming the German terms ("also called the TELC B1 Wortliste /
  Wortschatz"), which would not create German pages.

## Backlog changes
- Re-prioritised: B1/A1 list treatment done; A2/B2 treatment dropped (now pos 6.8 / 7.3 with good CTR).
- Added: printable/PDF list idea (query with "pdf"), start.html vs home overlap, fetch-cache note,
  Windsor data window.

## Next steps
- Next analytics run (from 2026-12-03): first look at B1/A1 CTR; judge properly after 2026-12-17
  (21 days). Judge articles guide on/after 2026-12-07.
- Content agent: tips guide expansion (lost position, 14.6) remains top content item.
