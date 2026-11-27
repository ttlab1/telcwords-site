# Changelog

Newest entries at the bottom. One entry per run: date (UTC), agent, what changed,
commits. Record every title/description change with old and new text.

## 2026-11-14 · setup
- Imported the live site (15 files, byte-identical to the server) as `a3b0281`.

## 2026-11-15 · setup
- Hostinger Git auto-deployment connected by the owner; verified: pushes go live in
  about 5–20 s, dotfiles included (`d7e2a2f`, `5d52c2c`).
- Added `.htaccess`: 301 www → non-www, http → https (`6d236f5`). www redirect
  verified live; http redirect ends at https but the server hop was not observed.
- Added `og-image.png` (1200×630) and og:image / twitter:image tags on all 9 pages;
  `twitter:card` changed from `summary` to `summary_large_image`; all sitemap
  `lastmod` set to 2026-11-15 (`20244bf`).
- Added `.agent/` (playbook, backlog, changelog, reports) and blocked it from the web.

## 2026-11-16 · content
- New page `telc-b1-vocabulary-by-topic.html`: 622 B1 words from `WORDS` in 10 topics,
  study notes, FAQ, search filter (`806e72b`). Target: "German/TELC B1 vocabulary by topic".
- Expanded `german-articles-der-die-das.html` from ~330 to ~1,800 words: reliability of
  each gender ending counted on 2,391 pooled A1–C1 nouns from `WORDS` (`61073aa`).
  Title old: `German Articles: How to Learn der, die, das (With Examples) | TELC Words`
  Title new: `German Articles der, die, das: Rules by Ending | TELC Words`
  Description old: `Practical rules and memory tricks for German noun genders der, die, das, with real example words from the TELC A1 list. Free practice game included.`
  Description new: `Which endings mean der, die or das? We counted 2,391 nouns from our TELC A1–C1 word lists. See how reliable each rule is, plus the key exceptions.`
  H1 old: `German Articles: How to Learn der, die, das`; new: `German Articles der, die, das: Rules by Ending`.
  Removed an unverified exam claim from its FAQ (points lost in named exam parts).
- Internal links to the new page from `start.html` (Guides; articles link text also
  updated), `telc-b1-vocabulary.html` and `telc-exam-vocabulary-tips.html`; sitemap now
  10 URLs; deploy probe updated (`c6e781c`). `index.html` untouched.

## 2026-11-16 · content (follow-up, ordered live by the owner)
- `WORDS` corrections in `index.html`, mirrored in the A2/B1 list pages. A2: Überfall
  die → der. B1 English: Bank "bench / bank", bestehen "to pass (an exam) / consist of",
  Blitz "lightning", Fahrplan "timetable / schedule", Handtuch "towel", Höhe "height /
  altitude", Illustrierte "illustrated magazine", Kritik "criticism / review", Medikament
  "medicine / medication", Mitbestimmung "co-determination / having a say",
  Nahrungsmittel "food / foodstuff", Pass "passport", Schein "banknote / certificate",
  See "lake", Sprechstunde "consultation hour", Technik "technology / technique",
  sich wenden "to turn to / contact". B1 articles added: das Gift, die Quittung.
  B1 spelling: naß → nass. Word counts per level unchanged (6,224).
- Game: new B1 topic mode (home-screen chips, `/?level=b1&topic=<key>`, separate
  `seen_B1_t_<key>` progress; personal best and wrong-word list shared with B1).
  Tested in headless Chromium: topic and normal play, deep links, session end, no errors.
- Topic page: 622 → 636 words (14 corrected words added), a "Play these N words" button
  per topic; title/description/H1 changed only in the number.
- Articles guide rebuilt from corrected data: 2,391 → 2,394 nouns, -ung 257 → 258.
- Later the same day (owner request): the home-screen "B1 by topic" section was replaced
  by a chooser that opens when the B1 card is tapped ("All B1 words" or one of 10 topics).
  Other levels start directly; deep links unchanged. Tested in headless Chromium.

## 2026-11-16 · technical-seo
- NOT verified live: the web fetch tool refused telcwords.com in this unattended run.
  Local checks and headless rendering passed. See the report.
  2026-11-17: owner confirmed live: deploy-check.txt shows this run's probe and the B2
  list page works on his phone.
- `site.webmanifest` fixed: name, dark colours, only existing icons (`96b9928`).
- 9 landing pages: footer link to the B1 topic page, "telc gGmbH" spelling, theme-color,
  underlined in-text links and focus outline; level pages: Play buttons deep-link to the
  level, table cells wrap on phones; guides: Article JSON-LD + og:type article; articles
  guide links to the topic page; sitemap lastmod. No title/description/h1 changes.
  `index.html` and `.htaccess` untouched.

## 2026-11-25 · distribution
- No site changes. Report `.agent/reports/2026-11-25-distribution.md`: GA4 referral check
  (Reddit 82 sessions / 60 % engaged in 28 days, steady daily, all to `/`), community rules
  research, drafts for r/German and Lemmy !german (articles-guide counts), 5 backlink targets.

## 2026-11-26 · analytics (also November monthly review)
- Data: Windsor trial gives only 30 days, so no previous-28-day comparison; halves + baseline used.
  Report `.agent/reports/2026-11-26-analytics.md`.
- `f0860cb` (Opus subagent, reviewed): B1 and A1 list pages; A2/B2/C1 unchanged as control.
  B1 title old: `TELC B1 German Vocabulary List (2,098 Words with English) | TELC Words`
  B1 title new: `TELC B1 Vocabulary List: 2,098 German Words with English | TELC Words`
  B1 description old: `Complete TELC B1 German word list with English meanings and articles: 2,098 words you can search, learn and practise free with the TELC Words game.`
  B1 description new: `All 2,098 TELC B1 German words with der/die/das and English meanings. Search the list, revise 636 words by topic, then practise free in a quick game.`
  B1 H1 old: `TELC B1 German Vocabulary List: 2,098 Words with English`; new: `TELC B1 Vocabulary List: 2,098 German Words with English`.
  A1 title old: `TELC A1 German Vocabulary List (1,099 Words with English) | TELC Words`
  A1 title new: `TELC A1 Vocabulary List: 1,099 German Words with English | TELC Words`
  A1 description old: `Complete TELC A1 German word list with English meanings and articles: 1,099 words you can search, learn and practise free with the TELC Words game.`
  A1 description new: `All 1,099 TELC A1 German words with der/die/das and English meanings. Search the list or browse it by letter, then practise free in a quick game.`
  A1 H1 old: `TELC A1 German Vocabulary List: 1,099 Words with English`; new: `TELC A1 Vocabulary List: 1,099 German Words with English`.
  og/twitter title+description mirror the new title/description. A1: contextual links to the
  articles guide and the A2 list. Sitemap lastmod for both; deploy probe.
  Before (GSC 2026-11-11 – 11-24): B1 96 impr, pos 7.3, 5 clicks; A1 31 impr, pos 6.5, 1 click.
  Do not change these titles/descriptions again before 2026-12-17.
- Verified live 2026-11-26 ~15:50 UTC (second fetch; first fetch returned a stale copy).

## 2026-11-26 · analytics follow-up (owner replied live)
- Owner approved the German-term sentence. All five level pages (A1–C1) got one English paragraph
  after the topic list: `In German, a list like this is called a Wortliste or Wortschatzliste. This
  page is the TELC Words <level> Wortliste, with the article and an English meaning for every word.`
  No title/description/H1 changes. Sitemap lastmod 2026-11-26 for the five pages; deploy probe.
  Note for judging the A1/B1 title test: this body sentence went live the same day on all five
  pages, so it does not distort the A1/B1 vs A2/B2/C1 comparison.
- Owner decisions recorded in PLAYBOOK §5: no paid Windsor plan (14+14-day method); scheduled
  agent runs switched to Opus.
## 2026-11-26 · owner request: game modes
- `index.html`: new game types chosen per level in the level sheet — Meanings (unchanged),
  Articles (der/die/das buttons; article pill hidden until answered; speech says the bare
  noun before answering). Plurals mode is built and tested but ships with an empty
  `PLURALS` table until the owner approves the Wiktionary (CC BY-SA 4.0) data.
  Deep links: `/?level=a1&mode=articles` (also `&topic=` for B1). Storage per mode:
  `pb_/aw_/seen_<LEVEL>_article`; Meanings keys unchanged. `WORDS` byte-identical.
- Articles guide: CTAs and level row now open the Articles game. Sitemap lastmod.

## 2026-11-27 · content
- `e87ad9c` (Opus subagent wrote, lead reviewed): NEW https://telcwords.com/german-separable-verbs-list.html
  — 138 separable verbs from the A1/A2/B1 `WORDS` lists (A1 18, A2 67, B1 53), grouped by prefix,
  stored English and first level; rules (word order, modal, subordinate clause, Perfekt incl.
  vorbereitet/zubereitet exception, zu-infinitive, stress), inseparable and über/um/unter/durch
  sections, FAQ (FAQPage), Article + BreadcrumbList JSON-LD, search filter, CTAs /?level=a1|a2|b1.
- Tips guide expanded (~305 → ~1,790 words): words-per-day table from list sizes, sample week,
  game modes, nouns/verbs/phrases, common mistakes, 5-item FAQ. No exam facts stated.
  Title old: `How to Learn TELC Vocabulary Fast: A Practical Study Plan | TELC Words`
  Title new: `How to Learn TELC Vocabulary: Study Plan & Tips | TELC Words`
  Description old: `A simple, realistic plan to learn German vocabulary for TELC exams: daily sessions, spaced repetition, articles, collocations and review of mistakes.`
  Description new: `How to learn German vocabulary for telc exams: words per day for each level, a weekly routine, game modes, and tips for nouns, verbs and phrases.`
  H1 old: `How to Learn TELC Vocabulary Effectively`; new: `How to Learn TELC Vocabulary: A Study Plan with Tips`.
  Before (GSC last 28 days to ~2026-11-25): 11 impressions, pos 10.7, 0 clicks. Judge from 2026-12-18.
- Links: start.html Guides list; one contextual sentence on A1/A2/B1 list pages; footer row on all
  10 landing pages got "Separable verbs list". No title/description changes on level pages (A1/B1
  title test unaffected: all level pages got the same kind of body edit). Sitemap: 11 URLs, lastmod.
  `index.html` untouched. deploy-check.txt = 2026-11-27T10:35:41Z.
- NOT verified live: the web fetch permission for telcwords.com was not answered in this unattended
  run (PROVENANCE_REQUIRED). Push confirmed on origin/main (e87ad9c).

## 2026-11-27 · owner approved plural game
- `index.html`: `PLURALS` filled with 1,654 reviewed nouns (from 1,978 Wiktionary matches;
  324 dropped by review: mass nouns, months, plurals with another meaning, doubtful forms).
  Home text mentions plurals; credit line (Wiktionary via german-nouns, CC BY-SA 4.0).
  `data/plurals.tsv` publishes the list under the same licence. `WORDS` byte-identical.
- Deep link `/?level=<lv>&mode=plurals`. Tested in headless Chromium: all 1,654 nouns give
  4 distinct options with exactly one valid plural; no JS errors.
