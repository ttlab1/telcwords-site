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
- `site.webmanifest` fixed: name, dark colours, only existing icons (`96b9928`).
- 9 landing pages: footer link to the B1 topic page, "telc gGmbH" spelling, theme-color,
  underlined in-text links and focus outline; level pages: Play buttons deep-link to the
  level, table cells wrap on phones; guides: Article JSON-LD + og:type article; articles
  guide links to the topic page; sitemap lastmod. No title/description/h1 changes.
  `index.html` and `.htaccess` untouched.
