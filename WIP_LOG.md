# WIP Log — holeshotbmx-landing

Append-only. **Any session — Cowork chat or Claude Code — that ends while leaving uncommitted or unpushed changes must add an entry here before finishing.** This is the single place to check "what's in flight and from where," without needing to dig through git diffs.

A chat session has no stable name to stamp here (the conversation title is a UI label only, not something a session can read about itself) — so identify by **date + what the work was about** instead. A Claude Code session should also note its branch name if one exists.

Format: `DATE | session type (chat/code) | branch (if any) | what changed | files | status`

Status values: `uncommitted` | `committed, not pushed` | `pushed, not merged`

---

- **2026-11-18** | unknown — found uncommitted, not made by the session that logged it | none (on `master`) | Android-launch site update: OG/Twitter meta copy changed from "coming soon" to "Now on Android," hero badge updated, two "Get it on Google Play" buttons added, waitlist button relabeled "Notify Me (iOS)" | `index.html` | pushed (bundled into the 2026-11-18 marketing/Cowork commit below)
- **2026-11-18** | chat (marketing/Cowork session) | none | Swapped both plain-text "Get it on Google Play" buttons for the official Google Play badge image (same link); refreshed 3 screenshots in the phone row (Track Finder, Live Race Tracker, Session Compare) with current app screens; added a "Live Race Tracker" feature card and updated "Performance Trends & PBs" copy for the new Compare To options; added this repo's `CLAUDE.md` and `WIP_LOG.md` | `index.html`, `CLAUDE.md`, `WIP_LOG.md`, `screenshots/track-finder-2026-11.png`, `screenshots/session-compare-2026-11.png`, `screenshots/live-race-tracker-2026-11.png` | pushed
- **2026-11-26** | code (cloud) | `claude/project-thread-18i18w` | Link previews + sitemap: new 1200x630 `og-image.jpg` share image replaces the 577x397 `logo.png` as og:image/twitter:image; OG + Twitter tags added to privacy/terms/support; sitemap now lists /, /support/, /privacy/, /terms/ with 2026-11-26 dates | `og-image.jpg`, `index.html`, `privacy/index.html`, `terms/index.html`, `support/index.html`, `sitemap.xml`, `WIP_LOG.md` | pushed, not merged (draft PR)
