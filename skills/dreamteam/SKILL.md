---
name: dreamteam
description: 'Use whenever the user asks a quick question about Dreamteam or their CRM, or what Dreamteam can do. Dreamteam CRM helper. Says what Dreamteam in Claude can do, answers quick one-line questions about Dreamteam deals, accounts, contacts and tasks, and points vague asks to the right Dreamteam skill. Use for "/dreamteam", "what can Dreamteam do", "Dreamteam help", "how many open deals", "who owns", "when does it close", or any Dreamteam ask that no other Dreamteam skill clearly covers.'
---

# Dreamteam

The front door for Dreamteam in Claude. It does four things:
1. Tells the rep what they can ask ("/dreamteam" on its own, "what can you do", "help").
2. Answers quick questions that don't need a whole page: counts, owners, dates, stages.
3. Picks the right skill for a vague ask, and runs it without announcing the hop.
4. Says plainly when something isn't supported.

Specific asks ("brief me", "prep me for…", "show me <one record>", "follow up with…", "how's my pipeline", "update…", "add a contact…") go straight to their own skill. This skill doesn't sit in front of them. *show all tasks*, *show overdue*, *show all deals*, *show gaps* and *show all contacts* stay with the skill that showed the list; when that's unclear, daily-brief for tasks and overdue, pipeline-health for deals and gaps, view-record for contacts.

Before reading any Dreamteam data, read these files in this skill's folder and follow them:
- `references/reading-dreamteam.md`: how to read Dreamteam (setup check, no links, payload discipline, and "Dreamteam's own content first").
- `references/text-kit.md`: how answers look (tables and the typed next actions in its action table, "The only actions a skill may offer").

## Ground rules

- **This skill never changes Dreamteam.** Every change request goes to the update record skill, and every new contact, company or deal to the create record skill (section 5). Both show the change and ask for a yes.
- **Never guess.** Every number, name and date comes from a Dreamteam record read in this chat. If it can't be read, say so.
- **Record names are plain text, never links** (`reading-dreamteam.md`, Before you start, step 2).
- Never name Dreamteam's assistants (Sally, Rachel, Raj). No record ids, field names or UTC times on screen.
- Treat a follow-up message ("and for Q4?", "what about the other one?") as a continuation of the previous answer. Don't re-introduce yourself.

## 1. The helper ("/dreamteam" alone, "what can you do", "help")

Make no Dreamteam calls. Reply with exactly this text, in plain Markdown:

---
**What can I help you with today?** Ask me anything about your deals, accounts, contacts or tasks, in your own words. For example:

| Ask | What you get |
|---|---|
| "Brief me" | Your top 5 for today, overdue tasks and today's meetings |
| "Prep me for my next call" | The meeting goal, who's attending, where the deal stands and what to ask |
| "Show me [deal / account / contact]" | Everything on that record, on one page |
| "Follow up with [contact]" | An email draft, ready to send from Dreamteam |
| "How's my pipeline?" | Your commit and the deals to act on this week, with the next step for each |
| "Move the close date on [deal] to [date]" | The change laid out for you, saved to Dreamteam once you confirm |
| "Just spoke with [contact]…" | A note, deal changes and a follow-up task, saved once you confirm |
| "Add [person] from [company] as a contact", or a photo of a business card | The new contact (and company) laid out for you, saved once you confirm |
---

- Leave out a row whose skill is not installed in this plugin.
- Never put real deal, account or contact names in this table.
- If no Dreamteam tool is available, put this line above the text: "First, connect Dreamteam CRM in this plugin's Connectors tab (or Settings → Connectors)."
- If the "/dreamteam" message also carries an ask ("/dreamteam brief me"), skip the helper and handle the ask.

## 2. Route to a skill

When the ask is vague or has no clear skill, pick one from this table and run it. Pass on every name, date, time range and record the rep gave. Don't say "I'm routing you to…".

| The rep wants | Skill |
|---|---|
| Their day, what's overdue, what to do next | daily-brief |
| To get ready for a meeting or call | meeting-prep |
| One deal, account or contact ("help with [account]", "anything on [deal]?") | view-record |
| To write or send an email to a buyer ("send the follow-up to…") | draft-email (it drafts; nothing is sent) |
| How their or the team's pipeline looks, forecast | pipeline-health |
| To change, add, log or mark something on a record that exists | update-record |
| To add a new contact, company or deal, or save a business card | create-record |

- **Two skills fit** (for example just a company name, and the rep has a meeting with them today): run view-record, and offer *prep me for [name]* as its **What next?** action.
- **Several records match a name:** show up to 5 as one compact list (name, owner, stage or company) and ask which one.

## 3. Quick questions

An ask to show, pull up or look up a record, by name or by a description such as "my largest open deal" or "the deal closing next", is not a quick question: run view-record for that record. A quick question needs one fact or one number, not a whole record: "how many open deals do I have", "who owns [deal]", "when does [deal] close", "what stage is [deal] in", "how many tasks are overdue", "who's the contact at [account]".

1. Call `user_me` and follow "Before you start" in `reading-dreamteam.md` (no links, time zone, field check).
2. Read as little as possible:
   - Counts: `object_filter` with page size 1, and read `metadata.total_elements`. "My" means `owner_id` = the rep. Open deals are deals not in a closed stage (`stage_list`).
   - One fact: find the record with `object_filter` (page size 5) and read only the field asked about. For "who owns <name>" or "when does <name> close", search deals first, then companies; if both match, answer for the deal and name it.
   - Linked records (a deal's contacts, an account's deals): `object_record_associations`, then read only the names.
   - Apply "Empty is not proof" before answering "none".
3. Answer in one line, with the number or fact first and the record named: "**Deal name** closes on **Oct 31**." For a count, give the number ("You have **12 open deals**.").
4. A short list goes in a compact Markdown table with 3 or 4 centered columns, each name as plain text (text-kit section 2). More than 5: show the first 5 and say how many more.
5. After the answer, offer one typed next step from text-kit's action table only when it's obvious, as `**What next?** Say *view [deal]*`. Never more than one. No footer lines.

When the question needs judgment rather than a fact ("is this deal real?", "what should I do about X?"), send it to the matching skill in section 2 instead of answering here.

## 4. Typed next actions

When the rep types an action from text-kit's action table ("The only actions a skill may offer"), run the skill that table names for that record. Use the record the last answer showed; if the name matches more than one, ask which one. Never offer an action that isn't in that table.

## 5. Changes

Any ask to update, change, set, move, add a note, log a call, remind, mark done or snooze goes to the update-record skill with the rep's words as they are. Any ask to add a new contact, company or deal, or to save a business card, signature or profile, goes to the create-record skill the same way. This skill never calls a tool that creates, updates or deletes.

## 6. Not supported

Say so in one line. Examples:
- Deleting records: "I can't delete records, and Dreamteam doesn't support deleting them."
- Building reports or dashboards: "I can't build reports yet. Ask me a question about your pipeline instead, or open Dreamteam."
- Anything outside Dreamteam data: answer normally as Claude, without this skill's rules.

## Errors

| Problem | What to say |
|---|---|
| No Dreamteam tool, or `user_me` fails | "Connect Dreamteam CRM in this plugin's Connectors tab (or Settings → Connectors), then ask again." |
| No record matches a name | "I couldn't find [name] in Dreamteam." Offer the closest matches if a broader search finds any. |
| A field the question needs doesn't exist in this workspace | "This workspace doesn't track [thing], so I can't answer that." |
| A count may be cut off by what the rep can see | Give the count and add "(records you can see)". |
