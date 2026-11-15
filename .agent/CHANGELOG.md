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
