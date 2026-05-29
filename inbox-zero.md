---
description: Process inbox to zero using GTD method
---

## Context

Use the installed Gmail MCP server to access Gmail. Follow the classification rules in .claude/CLAUDE.md for labeling.

## Your task

Process my inbox to zero following the Getting Things Done (GTD) method. Work through these steps:

### Step 1: Gather and classify

1. Search for emails `in:inbox` (both read and unread). **Important: paginate through ALL results** — use maxResults of 100 and keep fetching with pageToken until no more results are returned. Do not stop at the first page.
2. Read each email's subject, sender, snippet, and thread context
3. Classify each email into one of these GTD buckets:
   - **Action**: Needs my direct response or action → label with "01 Action" or "00 Action - Cust"
   - **Waiting For**: I'm waiting on someone else → label with "10 Waiting For"
   - **Archive**: Informational, no action needed → label with the appropriate category label from .claude/CLAUDE.md
   - **Spam**: Unsolicited junk → label with "Email Spam"
4. Apply the appropriate label to each email

### Step 2: Present summary for confirmation

Present a summary organized like a personal assistant briefing:

**🔴 Action Required** — Emails that need my response/action (with brief context on what's needed)

**⏳ Waiting For** — Emails where I'm waiting on others (with what I'm waiting for)

**📌 Things You Should Know** — Notable items from the archive pile. Anything interesting, important, or time-sensitive even if no action is needed. Be generous here — I'd rather hear about something irrelevant than miss something important.

**🗑️ Archived/Spam** — Brief count and summary of what was filed away

**⏰ Suggest Snoozing** — Any emails that aren't urgent but will need attention at a specific future time. Suggest when I should snooze them to.

### Step 3: Wait for confirmation

Ask me:

- Does this look right? Any re-classifications?
- Should I go ahead and archive + mark as read?
- Any of the snooze suggestions you want me to action?

### Step 4: Execute (after confirmation)

Once I confirm:

1. Remove the "INBOX" label from ALL emails (archive everything — action items live in their Action label, not the inbox)
2. Mark ALL processed emails as read
3. Report final counts
4. **Important**: Gmail's conversation view can show stale threads after bulk API changes. If the user reports ghost threads still in inbox, ask them to select all and archive in Gmail UI (`Ctrl+A` then `e`) to force a refresh.

## Important rules

- Never delete emails. Only add/remove labels.
- If I've already replied in a thread, it's NOT spam regardless of sender.
- When in doubt about classification, lean toward Action so I see it.
- Process ALL inbox emails, not just unread ones.
