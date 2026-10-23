# Dreamteam text kit: how every skill shows its answer

Every skill answers in **Markdown, written straight into the chat**. The skill decides **what** to show. This kit decides **how it looks**, so a rep learns the layout once. Where a skill's own layout differs from this kit (for example no numbers line, no Next column or no sort word in a heading), the skill wins.

Never draw a visual, widget, HTML page, artifact or file. Never use HTML tags (not even `<br>`). Text is faster, costs the customer less and renders the same on web and desktop.

## 1. The page, top to bottom

1. **Title line:** bold title only, no link. **It is the answer's first line.** Write nothing before it: no status line written before or while reading ("Pulling your day now", "Your brief is being assembled"), no opening sentence.
   `**Tuesday, Oct 14 · Your day**`
   The rep's own brief always says "Your day". Use a teammate's first name only for that teammate's brief ("Priya's day").
2. **Numbers line:** 2 to 4 numbers, each number in bold, separated by " · ".
   `**3** meetings ahead · **7** due today · **5** overdue · **1** new lead`
3. **Highlight (only where the skill lists one):** one quote block (`> `) of Dreamteam's own text or the skill's fixed fill-ins, such as pipeline-health's Bottom line or a meeting's Goal and Must ask. Never a line of your own, never a "key issue". At most one per page.
4. **Sections**, each with a `####` heading. Put a count or short qualifier in the heading after " · ": `#### Overdue · 5 · by priority`.
5. **Last line:** the **What next?** line where the skill has one (section 5), or a short "View all" line. No footer: no lines about the time zone, missing fields or what Claude couldn't see. Mention a time-zone or missing-field gap only when it changes the answer, in one short clause inside the section it affects.

Write nothing before the title and nothing after the last line. Never repeat the page as prose, never add advice.

**Nothing of your own between the blocks.** No opening summary after the title ("The main issue is…", "The key issue…"), no paragraph between sections, no closing advice or conclusion. Each block is exactly what the skill lists, in the form it gives, with the column names it gives.

## 2. Tables

Use a table whenever a section lists 2 or more similar items (tasks, deals, people, stages, changes, meetings).

- **Center every column:** the divider row is `|:---:|:---:|...` for every column.
- **At most 5 columns.** One fact per cell. Keep cells short (a few words) so columns stay readable. Put the long part (Dreamteam's reason) in one column only.
- **At most 5 rows** (the /dreamteam helper table is the one exception). For more, show the first 5 and add a plain line under the table: "<n> more · say *show all <things>*".
- When rows are records, the first column is the record name only, as plain text (no link, section 4).
- The rep is "you" in every cell, including owner columns. Teammates go by first name.
- **Each person once.** In any list of people (People, Key people, attendees, In the room), two rows are the same person when they share a contact id, an email address, or the same full name at the same company. Show one row, merge their buying roles (at most 2), and count them once in the heading. Never mention the duplicate on the page. A deal, company or task shows once per table too.
- Empty cell: leave it blank. Never write "N/A" or "-" for a missing value; "None" only where the column asks yes/no.
- Escape `|` inside a cell as `\|`.

### Empty cells, columns and sections

Check the finished answer for gaps before you write it. Nothing on screen should look broken or unfinished.

- **A column that is blank in every row:** leave the column out, heading included. This applies to any column except the first (for example Why (Dreamteam), Priority, Due, Reason, Owner). Never show a column with no values.
- **A cell that is blank in some rows:** leave it blank, as above. Don't fill it with text of your own.
- **A section with nothing in it:** leave the section out, heading included. Never show a heading with a count of 0 (no `#### Meetings ahead · 0`) and never a heading with nothing under it. A 0 may still appear on the numbers line, where it is useful.
- **A table with no rows:** leave it out. Never draw an empty table or a table of blank rows.
- **Placeholders:** never stand in for a missing value with "N/A", "-", "—", "TBD", "Unknown", "No data", "None found" or "(empty)", in a cell, a line or a heading. A label that is Dreamteam's own value (for example a qualification status of Unknown, or ICP Unknown) is a value, not a placeholder. The body of a draft email may hold bracketed gaps for the rep to fill (see draft-email), and the Now column of the update-record confirm table shows *(empty)* for an empty field.
- **Nothing at all to show:** the title line, the numbers line and one plain sentence saying what is empty, as the skill words it (for example "Nothing due today and no meetings.").
- **A skill's own empty line wins.** When a skill says to show a section with a set line when it is empty (for example pipeline-health's "No healthy signals on record this period."), show that line instead of leaving the section out.
- **Thin data gives a shorter page, never filler.** Many records hold little. Show what Dreamteam has and leave the rest out; never fill a gap with analysis, advice or a line about what wasn't found.

### Record names

- Show a deal's name without a trailing " - <date>" ending, everywhere it appears: tables, headings and typed actions. "Slack - Aug 31, 2026" shows as "Slack", "Update deal - Kestrel - Oct 12" as "Kestrel". Do this whether the name came from the deal record or from a task title.
- Record names are plain text, never links (section 4).

### Numbers

- Money under $10,000 in full: $8,600.
- From $10,000 to under $1M, in thousands with no decimals: $45K, $220K.
- From $1M, in millions with one decimal, never two: $2.5M, $15.9M (not $15.87M). Totals follow the same rule, so rounded rows may differ from the shown total by a rounding step.
- Percentages as whole numbers: 51%.
- Dates as "Oct 31" (add the year only when it isn't this year); times as "6:00 PM" in the rep's time zone.

### Sort order

- **Task tables: by priority**, High → Medium → Low, then tasks with no priority. Within the same priority keep My Day's order. Say "by priority" in the heading.
- **Deal tables: by amount**, largest first, unless the skill says otherwise (for example closing date). Say it in the heading: "largest first".
- **Meetings:** by start time.
- **Stages:** highest stage first.

## 3. Lists and short facts

- Facts and lines from one record: a bullet list, at most 3 bullets per section.
- Questions to ask: a numbered list, at most 3.
- No source tags on any line (no *[Dreamteam brief]*, *[email · Oct 12]*, *[CRM field: …]* or similar). Say where a detail came from only when the rep asks.
- Never add a line of your own: no analysis, summary, advice or "key issue". Where Dreamteam has nothing, leave the section out.
  - The only exceptions are the ones a skill itself lists: meeting-prep (a goal line and up to 3 questions when Dreamteam has no brief) and draft-email (the email's ask when Dreamteam has none). Each such line is marked **Suggested by Claude**. No other skill may add one.
  - Dreamteam's own inferred or debrief next steps start "Suggested (Dreamteam): ", so they never look like Claude's lines.

## 4. No links

- Never build URLs or hyperlinks to Dreamteam: not on record names, titles, table rows or typed actions, and no "Open in Dreamteam" lines.
- To see a record in the chat, the rep types *view <record>* (section 5).
- Never print a bare id, join link, phone number or passcode.

## 5. Next actions (typed, never buttons)

There are no buttons. The rep types what they want next, so every suggestion must be **specific**: it names the record, so it can't be confused with a row in another table. Write each typed action exactly as listed below, starting lowercase (*draft reply to Delta*, not *Draft reply to Delta*). Offer *prep me for…* only when a meeting with that record or person is coming up within the next 30 days (meeting-prep searches 30 days ahead for a named meeting).

- **Tables of tasks or deals:** a last column **Next** with one action per row, in italics: `*draft reply to Northwind*`, `*prep me for Brightline*`, `*accept Kestrel close date*`.
- **One-record pages** (view-record, meeting-prep): one line at the end, `**What next?** Say *<action>* · *<action>*`, 2 or 3 actions, each naming the record or person the way a rep would say it (short meeting name and day, first names), most useful first.
- **Other pages** that end with typed actions use the same wording: `**What next?** Say *…* · *…*`. Never "Next:" or "Want the full picture?".
- **draft-email and update-record:** no **What next?** line.
- Pick each action from what Dreamteam flags on that row (the task's type, a suggested change, a missing reply, a meeting today). Never a generic menu.

### The only actions a skill may offer

Offer only these. Never invent another action or wording that implies one.

| Typed action | Runs |
|---|---|
| *prep me for <deal or meeting>* | meeting-prep |
| *draft reply to <deal or contact>* (email task, reply needed; in the daily brief, also allowed on every Email Follow-up task) · *draft email to <contact>* (outreach) | draft-email |
| *view <deal, contact or company>* | view-record |
| *accept <deal> <field>* · *reject <deal> <field>* (Dreamteam's suggested change) | update-record |
| *review <deal> change* (shows the change, saves nothing) | update-record |
| *mark <deal> <task type> done* · *snooze <deal> <task type>* · *dismiss <deal> <task type>* | update-record |
| *create the suggested deal* · *reject the suggested deal* (Dreamteam's new-deal suggestion) | update-record |
| *add a note to <deal>* · *update <deal>* · *update <deal> close date* · *update <deal> amount* | update-record |
| *remind me <day> to <step> on <deal>* (a task for the rep's own internal work; the day the step names when it is after today, else the next weekday after today) | update-record |
| *update close dates* (every passed close date the page counted) | update-record |
| *show all tasks* · *show overdue* · *show all deals* · *show gaps* · *show all contacts* | the same skill, expanded list |

*dismiss* may be offered on any Recommended suggested task, whatever its type.

When the rep types one, run that skill for that record. Claude remembers what the page showed, so the record name is enough.

## 6. Dreamteam's suggested changes

Show a pending suggested change (an Update Deal task, or any suggestion with a current and a new value) as a table row:

| Deal | Change | Now → Suggested | Reason (Dreamteam) | Next |
|:---:|:---:|:---:|:---:|:---:|
| Kestrel | Close date | Oct 20 → Oct 30 | "Buyer moved the decision to month end" | *accept Kestrel close date* |

- The reason is Dreamteam's own text (`ai_reco_rationale` or the suggestion's description), word for word, shortened only by cutting.
- Never show the task's `confidence`, `composite_score` or `sort_rank`, and never describe them in words ("high confidence").
- Accept and reject always go to update-record, which shows the confirm table and saves only after a yes.

## 7. Confirm and done (update-record)

Before saving:

```
**Update Northwind (deal)?**

| Field | Now | New |
|:---:|:---:|:---:|
| Close date | Oct 20 | **Oct 30** |

Reply **yes** to save, or tell me what to change.
```

- A call recap may confirm several records at once: one table per record (note, deal, contact, task) under one "Reply **yes** to save".
- A group action confirms at most 5 records at a time.

After saving, one bullet per change: `- ✓ Close date → Oct 30` or `- ✗ Amount not saved: <reason>`, under `**Saved to Dreamteam**`.

## 8. Never

- No HTML, no widgets, no artifacts, no files, no images.
- No links to Dreamteam pages (section 4).
- No emoji except ✓ and ✗ in update-record results.
- No colour words standing in for status ("red", "green"), and no Red Flag / Amber / Green status anywhere. Say the fact: "2 days overdue". For qualification, name the areas not confirmed: "Pain, Champion not confirmed".
- No code blocks, except the email body in draft-email.
- No Confidence, Momentum, Risk, multi-threading, risk custom fields, risk details or risk ratings, on deals or tasks, and never use them to rank or pick items (see `reading-dreamteam.md`).
- No footer lines and no source tags.
- No empty columns, empty tables, sections with a count of 0, or placeholder text (section 2, Empty cells, columns and sections).
- No summary, analysis or advice of your own, and no "Next:" lines (use **What next?** or the skill's last line).
- About 30 lines at most, unless the skill sets its own limit. Cut rows before cutting sections.
