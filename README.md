# Dreamteam Sales

Ask Claude about your Dreamteam CRM in plain words: your day, your pipeline, your next meeting, or one deal, contact or company. Claude answers from your Dreamteam workspace, drafts follow-up emails, and adds or updates records after you confirm.

Dreamteam Sales connects only to Dreamteam, through the Dreamteam CRM connector (`https://mcp.dreamteamcrm.ai/mcp`), and sees only what your Dreamteam role allows. It stores nothing, changes records only after you reply **yes**, never deletes records and never sends email.

## What's inside

| Skill | Try asking | Access |
|---|---|---|
| Daily brief | "Brief me on my day", "What's overdue?" | Reads only |
| Pipeline health | "How's my pipeline?" | Reads only |
| Meeting prep | "Prep me for my next meeting" | Reads only |
| View a record | "Show me my largest open deal", "Who is Priya Shah?" | Reads only |
| Draft an email | "Draft a follow-up email for my biggest deal" | Reads only; drafts, never sends |
| Update a record | "Move the close date of my largest open deal to the last day of next month" | Writes only after you confirm |
| Add a record | "Add Priya Shah from Acme as a contact", or a photo of a business card | Writes only after you confirm |
| Dreamteam help | "What can Dreamteam do?" | Reads only |

Most answers end with short next steps you can type, such as *draft reply to Northwind*.

## Get started

1. Add Dreamteam Sales from the directory: **Customize → Plugins → Discover**, select **Dreamteam Sales**, then **Add**.
2. Open the plugin's **Connectors** tab and connect **Dreamteam CRM**. Sign in with your Dreamteam account. There's no API key to set up. On Team and Enterprise plans, an Owner adds the connector for the organization first.
3. Start a new chat and ask "Brief me on my day".

We recommend these tool permissions under **Customize → Connectors → Dreamteam CRM**: read tools **Always allow**, `object_create`, `object_update` and `task_reassign` **Needs approval**, and `object_delete` and `object_batch` **Blocked**. Dreamteam Sales never uses the last two. To revoke access, disconnect Dreamteam CRM there.

## Support and license

Help: https://support.dreamteam.ai/ or gethelp@dreamteam.ai. Licensed under Apache-2.0.
