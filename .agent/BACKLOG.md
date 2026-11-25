# Backlog

Ordered by expected value. Agents: tick items off with the date and commit, add new
findings at the right place, and keep this file short and current.

## Technical
- [x] 2026-11-16 (technical-seo): full audit of all 10 pages; fixes in the changelog.
- [x] 2026-11-17: owner confirmed the 2026-11-16 technical-seo deploy live.
- [x] 2026-11-17: owner granted web fetch access to telcwords.com; live checks work again.
      If fetch is refused in a scheduled run, report it at once.
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
- [ ] B1 list: 82 impressions at position 11 in the baseline period; first target
      for title/description/content improvement.
- [ ] A2 (position 14.9) and B2 (12.5) lists: same treatment.
- [ ] Monthly review: present German/Turkish query data to the owner
      ("telc b1 wortschatz", "telc a1 kelime listesi" at positions 50+).

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
