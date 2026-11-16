# Backlog

Ordered by expected value. Agents: tick items off with the date and commit, add new
findings at the right place, and keep this file short and current.

## Technical
- [ ] Full first audit against PLAYBOOK §4 (all 9 pages).
- [ ] Confirm from outside the browser that `http://telcwords.com/` answers with a
      301 from the server (so far only seen through a browser that may upgrade to
      https by itself).
- [ ] Find out, without risking a real page, what happens on the server when a file
      is deleted from the repo (use a throwaway probe file) and record the answer in
      PLAYBOOK §1.
- [ ] Review structured data per page type; add BreadcrumbList and FAQPage only
      where the page really contains that content.
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
- [ ] First drafts for r/German and r/languagelearning: a guide is live now; the
      counted der/die/das numbers (e.g. -er only 69 % der, Ge- only 40 % das) are the hook.
- [ ] Research free tool/resource lists for German learners that accept submissions.
