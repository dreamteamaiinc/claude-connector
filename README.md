# Dreamteam Sales for Claude

Ask Claude about your Dreamteam CRM in plain words: your day, your pipeline, your next meeting, or one deal, contact or company. Claude can also draft emails, add contacts and deals, and update records after you confirm.

## Set up

1. **Add the plugin.** In claude.ai or the Claude desktop app, go to **Customize > Plugins > Add > Upload plugin** and select the zip. In Claude Code, install `dreamteam-sales` from your marketplace.
2. **Connect Dreamteam.** See [CONNECTORS.md](CONNECTORS.md).
3. **Try it.** Start a new chat and type "Brief me on my day".

You need a Dreamteam account and a Claude plan that supports plugins and connectors.

## What you can ask

| Skill | Example |
|---|---|
| `daily-brief` | "Brief me on my day", "What's overdue?" |
| `pipeline-health` | "How's my pipeline?" |
| `meeting-prep` | "Prep me for my next meeting" |
| `view-record` | "Show me my largest open deal", "Who is Priya Shah?" |
| `draft-email` | "Draft a follow-up email for my biggest deal" |
| `update-record` | "Move the close date of my largest open deal to the last day of next month" |
| `create-record` | "Add Priya Shah from Acme as a contact", or send a photo of a business card |
| `dreamteam` | "What can you do?" |

Answers end with short next steps you can type, such as *draft reply to Northwind*.

## What Claude can do with your data

- **Reads** only what your Dreamteam account can see, through the Dreamteam connector. The plugin stores nothing.
- **Changes or adds** a record only after you reply **yes** to the change it shows you.
- **Never** deletes records or sends email.

## If something doesn't work

| Problem | Fix |
|---|---|
| Claude can't reach Dreamteam | Reconnect **Dreamteam CRM** in the plugin's **Connectors** tab |
| Times look off | Tell Claude your time zone, for example "I'm in Pacific time" |

## Support

gethelp@dreamteam.ai
