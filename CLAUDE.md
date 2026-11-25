# holeshotbmx-landing — CLAUDE.md

Project instructions for AI-assisted work on the Holeshot BMX landing site (holeshotbmx.com.au).

**Repo:** `C:\Users\ryan_\holeshotbmx-landing` — static site, deployed via GitHub Pages (`pages-build-deployment` Action on push to `master`).

## ⚠️ Standing rule — identify your session, log unfinished work

Ryan runs multiple chats and Claude Code sessions across his projects (this site, `bmx-performance-app`, and others). A session has no stable "name" it can stamp into files — a chat's conversation title is a UI label only, not something readable from inside the session — so identification works like this instead:

- **Claude Code sessions:** work on a descriptively-named branch (`claude/<short-task-slug>`), same convention as `bmx-performance-app`. The branch name + commit messages are the identity trail.
- **Any session (chat or code) that ends while leaving uncommitted or unpushed changes** must add an entry to `WIP_LOG.md` (same folder) before finishing — date, session type, branch if any, a one-line description of what changed, files touched, and status (`uncommitted` / `committed, not pushed` / `pushed, not merged`). Check that file first when asked "what's pending" instead of only reading `git status`.
- Prefer finishing and committing over leaving work in progress. If you do leave something uncommitted, the `WIP_LOG.md` entry is not optional.

## Notes

- `index.html`, `privacy/index.html`, `terms/index.html` fetch legal content from Supabase using the **publishable key** (`sb_publishable_...`) — see the main app's `CLAUDE.md` for the 2026-06-28 key rotation this depends on. If a page shows "Unable to load," check this key hasn't gone stale.
- Footer links (Privacy, Terms, Support, Instagram, YouTube) live in each page's own `<footer>` — there's no shared partial/include, so a new footer link needs adding to every page individually.
- **App Links / Universal Links (`https://holeshotbmx.com.au/app/*` opens the app):**
  - `.well-known/apple-app-site-association` (iOS) and `.well-known/assetlinks.json` (Android) prove the site trusts `com.holeshotbmx.app`. Don't rename or redirect them. Apple's file has no extension; GitHub Pages serves it as `application/octet-stream`. Apple's CDN accepts that, and Pages can't set headers anyway.
  - `.nojekyll` must stay. Without it, Jekyll skips dot-folders and `.well-known/` is never published.
  - `app/index.html`, `app/setup/index.html` and `404.html` are the **same page** (Pages has no rewrites; `404.html` catches any other `/app/...` path and shows "not found" for everything else). Edit all three together. The script reads the screen from the URL (`/app/setup` → `bmxapp://onboarding`), so the copies need no per-page edits.
  - These files change only if the Apple Team ID or the Android signing keys change.
