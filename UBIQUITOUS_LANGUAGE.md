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
| **Action Plan** | The structured, monthly-granularity roadmap for the current half-year (`action-plan.html`), covering มิ.ย.–พ.ย. 2569 for H2 2026 | Roadmap, plan |
| **Action Item** | A single short, near-term commitment shown in the homepage's Action Items list (e.g. "นัดคุย พี่อ้น + พี่ทอม") — glance-level, not the full monthly plan | Task, todo |
| **Discuss ActionPlan** | The recurring Monday ritual: review what shipped in the past week, note any urgent/interrupt work, and update the Action Plan page accordingly | Weekly sync, standup |

## Site structure

| Term | Definition | Aliases to avoid |
| --- | --- | --- |
| **Site Page** | A page that's part of the persistent nav (currently: Home, Action Plan) — as opposed to a standalone artifact | — |
| **Standalone Artifact** | A page not part of site nav because it has its own single-purpose layout and is consumed outside the site's browsing flow (Slide Deck, Email CEO) | — |

## Relationships

- A **Half-year Archive** contains exactly one **Slide Deck** and one **Email CEO**.
- The **Action Plan** is the full monthly breakdown for the *current, not-yet-archived* half-year; once that half-year ends, its content is folded into a new **Half-year Archive** and the **Action Plan** resets for the next cycle.
- **Discuss ActionPlan** is the process that keeps the **Action Plan** current; it does not modify **Action Items** (those are set/cleared ad hoc, not on a weekly cadence).
- **Site Pages** share a nav bar; **Standalone Artifacts** never do.

## Example dialogue

> **M2Dev:** "ทำไม Action Plan กับ Action Items ถึงเป็นคนละที่กัน?"
> **Dev:** "**Action Item** เป็น list สั้นๆ หน้าแรก — ของที่ต้องทำเร็วๆ นี้ ไม่ผูกกับเดือนไหนเป็นพิเศษ ส่วน **Action Plan** คือ roadmap เต็มรูปแบบ แบ่งเป็นรายเดือนทั้ง 6 เดือนของ half-year นี้"
> **M2Dev:** "แล้ว Discuss ActionPlan ทุกจันทร์ไปแก้ไฟล์ไหน?"
> **Dev:** "แก้ `action-plan.html` — เอาของที่ทำเสร็จอาทิตย์ที่แล้ว กับงานด่วนที่แทรกเข้ามา ไปอัปเดตในเดือนปัจจุบัน ไม่ไปแตะ **Action Item** list บนหน้าแรก เพราะอันนั้นเป็นคนละ cadence กัน"
> **M2Dev:** "พอครบ 6 เดือนแล้วไงต่อ?"
> **Dev:** "ตอนนั้นเนื้อหาทั้งหมดใน **Action Plan** จะถูกสรุปเป็น **Half-year Archive** ใหม่ (โฟลเดอร์ `2026-h2/`) แล้ว **Action Plan** ก็ reset เริ่มรอบใหม่"

## Flagged ambiguities

- "Action Plan" and "Action Item" sound like the same thing but are different granularities (monthly roadmap vs. glance-list) — kept as two distinct terms rather than merging, see ADR-0001 D1.
- The repo's newly-stated purpose "รวบรวมการทำงานฝั่ง dev" (aggregate dev-side work) was not fully unpacked — M2Dev did not confirm whether this means more content types beyond Dev Radar/Action Plan should live here. Left as an open item in ADR-0001, not modeled as a term yet.
