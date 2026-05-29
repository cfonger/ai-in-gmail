---
description: Review waiting-for items and follow up on stale ones
---

## Context

Use the installed Gmail MCP server to access Gmail. Follow the classification rules in .claude/CLAUDE.md.

## Your task

Review everything in my "Waiting For" folder and help me decide what needs a nudge.

### Step 1: Gather waiting-for items

Search for emails with the "10 Waiting For" label using `label:10-waiting-for in:anywhere` (the `in:anywhere` is important so snoozed/archived items aren't silently excluded). For each email, read the full thread to understand:

- What I'm waiting for
- Who I'm waiting on
- How long it's been
- Whether there's been any recent activity

### Step 2: Present status report

Organize items by staleness:

**🔴 Overdue / Going Cold** (no response in 5+ days) — These likely need a follow-up nudge.

**🟡 In Progress** (response within last 5 days) — Waiting is reasonable, but flag if deadline is approaching.

**🟢 Recent** (response within last 2 days) — No action needed, just FYI.

For each item, show:

- Subject and who you're waiting on
- What you're waiting for (specific deliverable/answer)
- Days since last activity
- Recommended action (nudge, wait, or close)

### Step 3: Work through follow-ups

For items that need a nudge, offer to:

- **Draft a follow-up**: Write a friendly nudge email
- **Escalate**: Draft a more direct follow-up if it's been too long
- **Close**: Remove "Waiting For" label if it's no longer relevant, apply appropriate archive label
- **Skip**: Move on

### Step 4: Summary

Wrap up with:

- How many items are in waiting-for
- How many got follow-ups today
- Any that should probably just be closed out

## Important rules

- Never delete emails. Only add/remove labels.
- When drafting follow-ups, never use emdashes.
- Follow-up tone should be friendly but clear — not passive-aggressive.
