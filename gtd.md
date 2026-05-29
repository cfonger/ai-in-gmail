---
description: Daily GTD email workflow
---

## Context

Use the installed Gmail MCP server to access Gmail. Follow the classification rules in .claude/CLAUDE.md.

## Your task

Run the full daily GTD email workflow. Work through these phases in order:

### Phase 1: Inbox Zero

Process the inbox to zero following the /inbox-zero command's approach:

1. Search for ALL emails `in:inbox` (paginate through all results)
2. Classify each email (Action, Waiting For, Archive, or Spam)
3. Apply labels per .claude/CLAUDE.md rules
4. Present a personal assistant briefing with action items, things to know, and snooze suggestions
5. Wait for confirmation, then archive everything and mark as read
6. If Gmail shows ghost threads after archiving, ask user to select all + archive in Gmail UI

### Phase 2: Action Review

Once inbox is zero, review action items following the /action-review approach:

1. Pull all emails labeled "01 Action" and "00 Action - Cust" (use `label:01-action in:anywhere` and `label:00-action---cust in:anywhere` — note the **three dashes** for 00 Action - Cust because the label has space-dash-space; without that and `in:anywhere`, snoozed/archived items will be silently excluded)
2. Present a prioritized list (urgency, impact, effort)
3. Flag 2-minute tasks for immediate completion
4. Work through items one at a time: reply, delegate, defer, or done
5. Draft replies as needed (user will copy-paste into Gmail Reply All)
6. For deferred items, add "05 Snoozed" label and tell user when to snooze in Gmail UI

### Phase 3: Waiting For Check (quick)

Do a quick scan of "10 Waiting For" items (use `label:10-waiting-for in:anywhere`):

1. Flag anything older than 5 days with no activity
2. Offer to draft follow-up nudges for stale items
3. Don't go deep here; save the full review for /waiting-for-review or /weekly-review

### Phase 4: Wrap-up

Summarize the session:

- Emails processed from inbox
- Action items completed
- Replies drafted/sent
- Items deferred (and when they'll come back)
- Items moved to Waiting For
- Anything notable the user should keep in mind today

## Important rules

- Never delete emails. Only add/remove labels.
- When drafting replies, never use emdashes. Use commas, periods, or semicolons instead.
- Inbox zero means literally zero. Action items live in their Action labels, not the inbox.
- User will copy draft text into Gmail Reply All for proper threading.
