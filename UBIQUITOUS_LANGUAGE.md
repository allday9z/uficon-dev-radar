# Ubiquitous Language — uficon-dev-radar

## Reporting cycle

| Term | Definition | Aliases to avoid |
| --- | --- | --- |
| **Dev Radar** | The half-yearly report artifact (slide deck + CEO email) summarizing dev team output for one half-year period | Dev report, sprint report |
| **Half-year Archive** | A dated folder (`YYYY-hN/`) holding the frozen `slide.html` + `email-ceo.html` for one past reporting cycle | Quarter, period folder |
| **Slide Deck** | The standalone, fullscreen 1280×720 presentation viewer (`slide.html`) delivered/presented for a Dev Radar cycle | Deck, presentation |
| **Email CEO** | The standalone, copy-paste-ready email mockup (`email-ceo.html`) sent to leadership summarizing a Dev Radar cycle | CEO update, email draft |

## Planning

| Term | Definition | Aliases to avoid |
| --- | --- | --- |
| **Discuss ActionPlan** | The recurring Monday process: Oracle asks M2Dev two questions (what shipped this week, what urgent/interrupt work came in), then records the answers as a new dated entry | Weekly sync, standup, Action Plan (superseded name) |
| **Discuss Entry** | A single dated markdown file (`discuss/YYYY-MM-DD.md`) recording one week's Discuss ActionPlan answers — the record of one interview, not a plan for the future | Log entry, note |
| **Action Item** | A single short, near-term commitment shown in the homepage's Action Items list (e.g. "นัดคุย พี่อ้น + พี่ทอม") — glance-level, unrelated to the weekly Discuss Entry cadence | Task, todo |

## Site structure

| Term | Definition | Aliases to avoid |
| --- | --- | --- |
| **Site Page** | A page that's part of the persistent nav (currently: Home, Discuss ActionPlan) — as opposed to a standalone artifact | — |
| **Standalone Artifact** | A page not part of site nav because it has its own single-purpose layout and is consumed outside the site's browsing flow (Slide Deck, Email CEO) | — |

## Relationships

- A **Half-year Archive** contains exactly one **Slide Deck** and one **Email CEO**.
- **Discuss ActionPlan** is a process, not a document; each run of that process produces one **Discuss Entry**. `discuss.html` lists all **Discuss Entries** newest-first, each linking to its file on GitHub.
- **Discuss ActionPlan** does not modify **Action Items** — those are set/cleared ad hoc on the homepage, a separate cadence from the weekly interview.
- **Site Pages** share a nav bar; **Standalone Artifacts** never do.

## Example dialogue

> **M2Dev:** "ทำไม Action Item บนหน้าแรก กับ Discuss ActionPlan ถึงเป็นคนละที่กัน?"
> **Dev:** "**Action Item** เป็น list สั้นๆ หน้าแรก — ของที่ต้องทำเร็วๆ นี้ ไม่ผูกกับสัปดาห์ไหนเป็นพิเศษ ส่วน **Discuss ActionPlan** คือกระบวนการที่ผมถามคุณทุกจันทร์ แล้วบันทึกเป็น **Discuss Entry** ใหม่"
> **M2Dev:** "แล้วทุกจันทร์ทำไฟล์ไหน?"
> **Dev:** "สร้าง **Discuss Entry** ใหม่ที่ `discuss/YYYY-MM-DD.md` — บันทึกสิ่งที่คุณตอบ 2 ข้อ: ทำอะไรเสร็จ กับมีงานแทรกอะไรเข้ามา แล้วเพิ่ม card ใหม่บน `discuss.html`"
> **M2Dev:** "ไม่มีการวางแผนล่วงหน้าเลยเหรอ?"
> **Dev:** "ไม่มี — **Discuss ActionPlan** เป็นบันทึกสิ่งที่เกิดขึ้นแล้ว (retrospective) ไม่ใช่ roadmap ล่วงหน้าแบบที่เคยลองทำใน ADR-0001 ตอนแรก"

## Flagged ambiguities

- The original "Action Plan" term (ADR-0001) meant a pre-drafted monthly roadmap page. M2Dev corrected this (2026-07-06, see ADR-0002): the real need was a retrospective interview-and-log process, now called **Discuss ActionPlan** / **Discuss Entry**. The old term is kept in ADR-0001 as historical record but should not be used going forward.
- The repo's newly-stated purpose "รวบรวมการทำงานฝั่ง dev" (aggregate dev-side work) was not fully unpacked — M2Dev did not confirm whether this means more content types beyond Dev Radar/Discuss ActionPlan should live here. Left as an open item, not modeled as a term yet.
