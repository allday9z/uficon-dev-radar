# ADR-0001: H2 2026 Action Plan page + site navigation

**Status**: Proposed — grilling session asked live questions, M2Dev did not respond within two 60s windows (away from keyboard). Decisions below use the recommended option from each question and should be reconfirmed via Telegram before pushing live.

## Context

M2Dev asked for four things on this repo in one request:

1. A "6-Month Action Plan (มิ.ย.–พ.ย. 2569)" document/page.
2. A `/grill-with-docs` session to sharpen the design (this doc is part of that output).
3. A new, separate navigation menu item on the site.
4. A recurring Monday reminder to "Discuss ActionPlan" — summarize the week's work + urgent/interrupt work.

M2Dev also stated the repo's purpose for the first time: **"รวบรวมการทำงานฝั่ง dev"** — aggregate/consolidate dev-side work.

The repo today is three static files: `index.html` (a card grid, one card per half-year archive, plus a hardcoded "Action Items" list), and `2026-h1/{slide.html,email-ceo.html}` (a self-contained slide-deck viewer and an email-mockup-to-copy-paste, respectively — neither is a "site page," both are standalone artifacts with their own layout conventions and no nav).

## Questions asked (grilling)

1. Does the new Action Plan page replace/absorb the existing "Action Items" list on `index.html`, sit alongside it, or expand that list in place?
2. Does the new nav need to be a real top nav bar across pages, or just another card/link on the homepage?
3. Is this repo staying a twice-yearly snapshot artifact, or becoming a living, continuously-updated index?

No response received (two AskUserQuestion rounds, 60s each, user away). Proceeding on the recommended defaults, flagged for reconfirmation.

## Decisions

### D1 — Action Plan is a new page, existing Action Items list stays as-is

`action-plan.html` is a new, separate page with a monthly breakdown for มิ.ย.–พ.ย. 2569 (June–November 2026). The existing "Action Items" section on `index.html` is left untouched — it's the short, current "next meeting" list; the new page is the fuller structured plan. The `index.html` Action Items section links out to the full plan page instead of trying to hold the whole 6-month breakdown inline.

**Why not merge:** the two lists serve different granularities — a glance-list vs. a monthly roadmap. Collapsing them into one would make the homepage either too sparse or too cluttered.

### D2 — Real top nav bar, added only to "site pages"

Add a persistent top nav (Home / Action Plan / Archive) to `index.html` and `action-plan.html`.

`slide.html` (fullscreen 1280×720 deck viewer) and `email-ceo.html` (a mockup meant to be copy-pasted into an actual email, already has its own `.back` link to `../`) are **not** touched — they are standalone artifacts, not site pages, and forcing a nav bar into either would fight their existing single-purpose layouts.

### D3 — Repo stays a periodic snapshot artifact, not a live system

No dynamic/build system introduced. The Action Plan page is hand-edited content, same as the existing half-year cards. What changes: the new weekly Monday reminder (separately implemented, see below) gives a standing cue to open this page and hand-update it — but the page itself stays static HTML, no backend.

**Why not build a living index now:** M2Dev's stated purpose ("รวบรวมการทำงานฝั่ง dev") is new information, not yet validated against what content M2Dev actually wants aggregated. Building live infrastructure before that's confirmed would be scope creep on an unconfirmed premise.

## Monday reminder (separate from the doc, implemented directly)

A macOS crontab entry (`0 9 * * 1`) runs `~/.claude/skills/dev-radar-monday-reminder/remind.sh`, which sends a Telegram message prompting M2Dev to summarize the week's completed work + any urgent/interrupt work, and update the Action Plan. Chosen over the Claude-Code `CronCreate` tool because that tool is session-scoped and auto-expires after 7 days — inadequate for a standing weekly ritual. Chosen over a CLAUDE.md standing rule because a rule only fires when a session happens to start on a Monday, not proactively.

Rollback: `crontab -e` and delete the `dev-radar-monday-reminder` line; delete `~/.claude/skills/dev-radar-monday-reminder/`.

## Open items to reconfirm with M2Dev

- Whether D1/D2/D3 match intent (asked, unanswered — recommended defaults used).
- Actual content owners/dates for August–November 2026 in the Action Plan — placeholder rows only, meant to be filled via the new Monday ritual.
