# Backlog

Ordered by expected value. Agents: tick items off with the date and commit, add new
findings at the right place, and keep this file short and current.

## Technical
- [x] 2026-11-16 (technical-seo): full audit of all 10 pages; fixes in the changelog.
- [x] 2026-11-17: owner confirmed the 2026-11-16 technical-seo deploy live.
- [x] 2026-11-17: owner granted web fetch access to telcwords.com; live checks work again.
      If fetch is refused in a scheduled run, report it at once.
      2026-11-26: a first fetch can return a stale copy (even pre-11-15 files); always use a
      fresh, unique query string and re-fetch before concluding a deploy failed.
- [ ] index.html head: og:site_name, WebSite JSON-LD, theme-color; link to /start.html
      (only in a run that can verify live).
- [ ] 320 px overflow on level pages, topic page and articles guide (6–52 px).
- [ ] Proposal: contrast of white text on the green das badge (~2.3:1).
- [ ] Manifest has no 192/512 px icons (needs a logo export from the owner).
- [ ] Confirm from outside the browser that `http://telcwords.com/` answers with a
      301 from the server (so far only seen through a browser that may upgrade to
      https by itself).
- [ ] Find out, without risking a real page, what happens on the server when a file
      is deleted from the repo (use a throwaway probe file) and record the answer in
      PLAYBOOK §1.
- [x] 2026-11-16: structured data reviewed; Article added on the two guides.
- [ ] Proposal only: viewport `user-scalable=no` in `index.html` (accessibility).
- [ ] Submit sitemap / verify site in Bing Webmaster Tools (needs the owner; Bing
      already sends about half as many organic visits as Google).

## Content
- [ ] Expand `telc-exam-vocabulary-tips.html` (about 340 words) into a full guide.
- [x] 2026-11-16 (`61073aa`): expanded `german-articles-der-die-das.html` (rules by
      ending counted on 2,391 nouns).
- [x] 2026-11-16 (`806e72b`): `telc-b1-vocabulary-by-topic.html` (622 words, 10 topics
      on one page). Do not split into per-topic pages unless Search Console shows
      per-topic queries; that would risk thin/duplicate pages.
- [ ] A2 topic page with the same approach (after the B1 page shows impressions).
- [ ] "How many words do you need for TELC A1/A2/B1/B2/C1" explainer.
- [ ] Printable / PDF-friendly word list (query "wortschatz c1 deutsch liste pdf telc" at pos 9):
      e.g. a print stylesheet for level pages; check demand again first.
- [ ] Per-level study plans (for example "TELC B1 in 8 weeks: vocabulary plan").
- [ ] Verb pages per level (separable verbs, verbs with prepositions) from `WORDS`.
- [ ] Exam explainer pages (format of each TELC level), facts verified on telc.net.

## Owner decisions
- [x] 2026-11-16: owner approved; 21 `WORDS` entries corrected (see changelog).
- [ ] Windsor.ai is a trial with only 30 days of history; fine for 28-day reports, but
      period-over-period comparison (28 vs previous 28 days) will not work.

## Analytics follow-ups
- [ ] Articles guide title/description changed 2026-11-16: do not change again before
      2026-12-07; judge effect then.
- [x] 2026-11-26 (`f0860cb`): B1 and A1 list titles/descriptions/H1 lead with "Vocabulary List";
      judge from 2026-12-17 against A2/B2/C1 (unchanged control group). Before: B1 96 impr /
      pos 7.3 / CTR 5.2 %, A1 31 / 6.5 / 3.2 % (GSC 2026-11-11 – 11-24).
- [x] 2026-11-26: A2/B2 treatment dropped for now: both at pos ~7 with CTR 14–20 %.
- [x] 2026-11-26: monthly review: German/Turkish query data shown to the owner; recommended
      staying English-only. Optional: one English sentence per level page naming "Wortliste /
      Wortschatz" (needs the owner's OK). Repeat in the December monthly review.
- [ ] start.html lost position (4.6 → 14.0) while `/` gained; check overlap of the two for
      generic "telc vocabulary" queries before changing anything.
- [ ] Windsor trial: only 30 days of history, no previous-period comparison. Keep the halves
      method or ask the owner about a plan.

## Distribution
- [x] 2026-11-25: drafts for r/German and Lemmy !german (der/die/das counts) given to the
      owner. r/languagelearning excluded: its rules require multi-language products.
- [x] 2026-11-25: 5 backlink targets given (UMich library guide, UMich Germanic portal,
      Hunter LibGuide, Tsimpliarakis cheat sheet, awesome-german). Do not repeat before
      2027-02 unless the owner reports a reply.
- [ ] Next run: ask the owner/data whether the r/German post went out; measure it. Next hook:
      B1 topic mode with a real excerpt from TOPICS.B1 (r/German at earliest 2026-12-23).
- [ ] r/German wiki "Free interactive courses, exercises and tests" page: suggest via modmail.
- [ ] Verify r/German and r/deutsch rules directly (reddit.com not fetchable in runs so far).
