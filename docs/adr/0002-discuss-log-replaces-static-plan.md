# ADR-0002: Discuss ActionPlan log replaces the static Action Plan page

**Status**: Accepted (M2Dev corrected ADR-0001's D1/D3 directly, in-session, 2026-07-06)

## Context

ADR-0001 built `action-plan.html` as a hand-authored, static monthly-breakdown page (มิ.ย.–พ.ย. 2569), on the recommended-default assumption that the repo should stay "a periodic snapshot artifact, not a live system" (ADR-0001 D3). That assumption was explicitly wrong.

M2Dev's correction, verbatim: "อันนี้ไม่ใช่ action plan ที่ฉันต้องการ ... ฉันต้องการ ระบบ discuss และสรุปงานทุกวันจันทร์ ทำเป็น github คอยบันทึกข้อมูลกันนะครับ ลงงาน และคุณคอยถามผมว่ามีงานอะไรพวกนี้แล้วคุณค่อยสรุปอีกที" — this isn't a document to hand-fill in advance, it's a **recurring interview-and-record process**: every Monday, Oracle asks M2Dev directly, then writes the summary. The artifact is the log of that process, not a pre-drafted roadmap.

## Decision

Replace `action-plan.html` (deleted) with:

- `discuss/YYYY-MM-DD.md` — one file per Monday session, containing what M2Dev answers to two standing questions (see `discuss/README.md` for the exact questions and template).
- `discuss.html` — a site page listing entries newest-first, each linking to its `.md` file's GitHub blob view (GitHub renders markdown natively there — no client-side markdown parser needed, keeping this repo dependency-free).
- Nav label changed from "Action Plan" to "Discuss ActionPlan" across `index.html`/`discuss.html`, and the Monday Telegram reminder's wording updated to ask the two questions directly rather than vaguely "อัปเดต Action Plan."

The **process** (Oracle actively asking, not waiting to be asked) is documented in `discuss/README.md` as a standing instruction for whichever Oracle session picks up after a Monday reminder fires — this can't be automated purely by cron since it requires an actual conversation, so the crontab's role stays limited to firing the Telegram nudge (see ADR-0001's Monday reminder section, unchanged).

## What stays from ADR-0001

D2 (real top nav, only on site pages, not on `slide.html`/`email-ceo.html`) and the Monday crontab mechanism itself are unaffected by this correction — only the *content model* of what Monday produces changed, from "edit a pre-drafted plan" to "record an interview."

## Consequence

`docs/adr/0001-h2-action-plan-and-nav.md` is left as-is (not deleted) — it's an accurate record of the original (wrong) design and the reasoning that led to it, useful for anyone wondering "why does discuss/README.md exist" later. This ADR supersedes its D1 and D3 only.
