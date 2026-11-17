# 2026-11-16 · technical-seo run (first)

## Important: live verification was NOT possible in this run
The web fetch tool refused every telcwords.com URL (deploy-check.txt, robots.txt,
sitemap.xml, home page; with and without a cache-busting query) because it asked for an
interactive permission that nobody could grant in an unattended run. The cloud shell
cannot reach the site either, and no other route was tried (playbook §3). So: all changes
below were pushed to `main` and verified locally (checks + headless Chromium), but
nobody has yet seen them on the live site. Deploy probe written in this push:
`2026-11-16T09:59:10Z deploy probe: technical-seo run` — https://telcwords.com/deploy-check.txt
should show exactly that line. The live-only checks (redirects, live robots/sitemap,
.agent blocked) were not done for the same reason.

## Update 2026-11-17: verified live by the owner
The owner opened https://telcwords.com/deploy-check.txt (showed the probe line of this
run) and https://telcwords.com/telc-b2-vocabulary.html on his phone and confirmed both
work correctly. Later on 2026-11-17 the owner granted web fetch access and the agent verified live:
deploy-check.txt = this run's probe; robots.txt correct; sitemap.xml has 10 <loc>, contains
the topic page and 2026-11-16, no old dates; A1 page: header and sticky Play buttons go to
/?level=a1, footer has "B1 words by topic" and "telc gGmbH"; articles guide (cache-busting
query): footer link, new in-text sentence and gGmbH present. Note: the fetch tool twice
summarised the sitemap wrongly (9 URLs, 2026-10-24); a yes/no question gave the real
content. Ask the tool narrow yes/no questions for verification.

## Audited (repo, all 10 HTML pages + config files)
- §4 on every page: one title, one description (137–154 chars), self canonical, one h1,
  lang=en, viewport, GA4, OG/Twitter incl. og:image, JSON-LD parses, html.parser OK.
  Titles and descriptions are unique. 289 internal hrefs, 0 broken. Sitemap well-formed,
  10 unique URLs, matches the 10 pages; robots.txt allows all and names the sitemap.
- Heading structure is sound (h1 → h2 → h3). No images in pages, so no image weight or
  layout-shift issues; the only render-blocking resource is the Google Fonts stylesheet
  (preconnect + display=swap already in place).
- Findings fixed: see below. Findings left: see "Not done".

## Changed
1. `site.webmanifest` (`96b9928`): was name "", white colours and two icon files that do
   not exist (404 on install/"add to home screen"). Now name/short_name "TELC Words",
   dark colours, start_url "/", icons = the existing 180 px and 32 px PNGs.
2. One commit for the 9 landing pages + sitemap:
   - Footer of all 9 pages: new link "B1 words by topic" (the topic page was linked from
     only 4 pages); "telc gmbh" → "telc gGmbH" (11 places, footer note and FAQ text).
   - Five level pages: header and sticky "Play free" buttons now open the game at that
     level (`/?level=a1` … `c1`) instead of the home screen.
   - `<meta name="theme-color" content="#0f0f13">` on all 9 pages.
   - Accessibility: in-text links are underlined (were colour-only); visible keyboard
     focus outline on links, FAQ summaries and the search box.
   - Mobile: level-page tables pushed the page 17–116 px wider than a 375 px screen
     (long unbreakable entries); `td{overflow-wrap:anywhere}` fixes it (375 px: no
     horizontal scroll on any page).
   - Articles guide: in-text link to the B1 topic page.
   - Structured data: `Article` JSON-LD (headline, description, dateModified, publisher;
     no datePublished because the original date is unknown) and og:type=article on the
     two guides. Other pages keep BreadcrumbList / FAQPage / ItemList / WebApplication.
   - sitemap.xml: lastmod 2026-11-16 on all 10 URLs.
   No title, description or h1 changed. `index.html`, `.htaccess`, `robots.txt` untouched
   (git diff empty). No vocabulary row changed.

## How the work was done
Audit, plan and review in the main session; edits 1–2 executed by an Opus subagent from a
written brief (exact-match replacements with asserted counts). Review: read the full
word-level diff, viewed the 375 px screenshots, re-ran the checks; the table-wrap fix
was added and measured in the main session.

## Local verification
Self-check script: 0 failures. Headless Chromium at 375 and 1200 px on all 9 landing
pages: no console errors (only blocked Google requests), list search works, focus outline
visible, footer and underlines render correctly.

## Not done / open
- index.html (not edited without live verification): proposals for next run —
  add og:site_name, a WebSite JSON-LD node and theme-color in the head; link to
  /start.html from the home-screen link block. Viewport `user-scalable=no` remains a
  proposal only (owner decision; accessibility vs. gameplay).
- http → https 301 from outside a browser, and the "what happens when a file is deleted"
  probe: both need live fetches; still open.
- At 320 px wide (very small phones) level pages, the topic page and the articles guide
  still overflow by 6–52 px. Minor; next run.
- Article badges: white text on the green "das" badge has low contrast (~2.3:1). It is
  the game's colour code, so proposed rather than changed.
- Level-page ItemList JSON-LD has only numberOfItems (valid, but gives no rich result);
  level-page titles are 68–70 chars (may be cut in results) — left to the analytics agent.
- Manifest still has no 192/512 px icons (none exist; would need a proper logo export).
