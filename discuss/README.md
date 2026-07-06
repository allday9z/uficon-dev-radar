# Discuss ActionPlan — log format

One markdown file per Monday session, named `YYYY-MM-DD.md` (the Monday's date).

## When M2Dev opens a session after the Monday Telegram reminder fires

Oracle should proactively ask (don't wait to be asked):

1. "สัปดาห์นี้ทำอะไรเสร็จบ้าง?" (what got done this week)
2. "มีงานด่วน/งานแทรกอะไรเข้ามาไหม?" (any urgent/interrupt work)

Then write a new `discuss/YYYY-MM-DD.md` using the template below, and add a card
for it at the top of `discuss.html`'s `.entries` list, linking to
`discuss-entry.html?id=YYYY-MM-DD` (the in-site markdown+Mermaid viewer — not a
raw GitHub link). Mark the previous latest entry's `entry-tag` span removed,
new one gets it.

Mermaid diagrams are supported: use a fenced ` ```mermaid ` code block anywhere
in the entry and `discuss-entry.html` renders it client-side.

## Entry template

```markdown
# Discuss ActionPlan — YYYY-MM-DD (สัปดาห์ ช่วงวันที่)

## งานที่ทำเสร็จสัปดาห์นี้

- ...

## งานด่วน/งานแทรก

- ...
```

Commit + push to `main` (GitHub Pages auto-deploys) after every entry, same as
any other change to this repo — confirm with M2Dev first per standing repo
authorization rules.
