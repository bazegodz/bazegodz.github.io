# Project instructions for AI agents

This file is the shared rulebook for every AI coding agent working in this repo
(Claude Code reads it through `CLAUDE.md`; Antigravity and other tools read it directly).
Keep project rules here, in one place, so all agents follow the same ones.

## What this repo is

The public website for **SOVEREIGN**, the internal publishing tool of the **BazeGodZ** podcast.
SOVEREIGN uploads the podcast's own clips to the BazeGodZ YouTube channel and schedules them.

It is served by GitHub Pages at `https://bazegodz.github.io/`, straight from the repo root.
There is no build step, framework, or package manager: what is committed is what is live.

| File | Purpose |
| --- | --- |
| `index.html` | Homepage: what SOVEREIGN is and who uses it |
| `privacy.html` | Privacy policy for SOVEREIGN's Google/YouTube access |

## Why these pages matter

These pages are the homepage and privacy-policy links that Google checks for
SOVEREIGN's OAuth consent screen. Breaking them can break SOVEREIGN's Google
verification and stop uploads. So:

- **Never rename, move, or delete `index.html` or `privacy.html`.** Their URLs are registered with Google.
- **Keep the privacy policy true.** It must match what SOVEREIGN actually does.
  It currently states the only scope is `youtube.upload`. If SOVEREIGN gains a
  scope or starts storing new data, update `privacy.html` in the same change and
  bump its "Last updated" date.
- **Keep the required links in `privacy.html`:** Google API Services User Data Policy
  (Limited Use), YouTube Terms of Service, Google Privacy Policy, and the
  revoke-access link.
- **Keep the homepage linking to `privacy.html`** and showing the contact email
  `bazegodzpodcast@gmail.com`.
- The app name **SOVEREIGN** and brand **BazeGodZ** must be spelled exactly like this.

## Cloud sessions vs. the owner's PC (read this first)

Most BazeGodZ work happens in Claude Code sessions on the owner's own PC. Those
sessions can see the local drives, the SOVEREIGN vault (`H:\My Drive\SOVEREIGN`),
the footage drives, Premiere and Pro Tools, and they keep memory between sessions.
**A cloud session (claude.ai/code) sees none of that. It sees only this repo, and
it starts with no memory of earlier work.** So, in a cloud session:

**Can be done here:** edits to `index.html` and `privacy.html`, wording and design
changes to the site, and changes to these rule files, always on a branch with a
pull request.

**Must be done on the owner's PC instead:** anything involving SOVEREIGN's code or
scheduled jobs, YouTube uploads, video or audio editing, the shorts and long-form
pipelines, the vault, footage, or client and business files. If a request needs
any of these, stop and tell the owner to do it in a desktop (local) session.
Don't try to rebuild it from scratch here.

**Never ask for, accept, or commit secrets or private code.** Do not ask the owner
to upload SOVEREIGN's code, the vault, or any file from their drives to GitHub.
In particular, never commit `client_secret.json`, `token.json`, `*.expired*.json`,
API keys, passwords, or anything from `08-SYSTEM/publish/` except the site pages.
This repo is public: anything committed here is visible to the whole internet,
even after it's deleted. If the owner offers such files, refuse and explain why.

The live copy of the two site pages also exists in the vault at
`08-SYSTEM/publish/site/`. After a change here is merged, the local session should
copy the pages back there so the two stay identical.

## How to work here

- Plain, hand-written HTML and inline CSS. No frameworks, build tools, trackers,
  analytics, or third-party scripts unless the owner asks for them.
- Match the existing style: `system-ui` font, 640px centered column,
  link color `#8a6a1f`. Pages must work on a phone.
- Check changes by opening the HTML file in a browser before committing.
- Work on a branch and open a pull request; don't push straight to `main`.
- **One agent at a time per file.** If more than one agent is in use, give each
  its own branch so they never edit the same file at the same time.
- Write commit messages in plain English that say what changed and why.

## About the owner

The owner is not a full-time developer. Explain changes in plain language,
recommend one option instead of listing many, and ask before anything that is
hard to undo or that is published outside this repo.
