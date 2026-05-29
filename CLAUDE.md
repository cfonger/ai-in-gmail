# Gmail Auto-Labeling Instructions

## Tool Usage Notes

- `mcp__gmail__search_emails`: `maxResults` must be a **number** (e.g. `100`), not a string (`"100"`). The tool will error otherwise.
- **Always include `in:anywhere` when searching by label** (e.g. `label:01-action in:anywhere`). Gmail's default search excludes snoozed and archived messages, so items that are snoozed or already in an archive sublabel will silently go missing without `in:anywhere`. This is especially important for Action, Waiting For, and Snoozed label sweeps.
- **Gmail label encoding for search**: every space in a label name becomes a `-`, and existing dashes stay as `-`. So `00 Action - Cust` encodes as `label:00-action---cust` (three dashes: space, dash, space). `10 Waiting For` is `label:10-waiting-for`. `01 Action` is `label:01-action`. **Common gotcha**: labels with `-` (space-dash-space) become three dashes in the search, not one. When in doubt, open the label in the Gmail UI and copy the value from the URL bar's search field.
- **Exact label search syntax for the most-used labels** (always confirm by also checking Gmail UI counts):
  - `01 Action` → `label:01-action in:anywhere`
  - `00 Action - Cust` → `label:00-action---cust in:anywhere`
  - `10 Waiting For` → `label:10-waiting-for in:anywhere`
  - `05 Snoozed` → `label:05-snoozed in:anywhere`
- For any Linear notification emails, use the Linear MCP (`mcp__linear-server__get_issue`) to fetch the full issue details (title, description, comments, status) for better context when briefing.

## How to Label Emails

When processing emails, apply ONE label from the categories below based on the email content. Use the label ID when applying labels via the Gmail API.

## Active/Action Labels

Use these for emails requiring attention:

| Label                | ID                                      | When to Use                                                                                                      |
| -------------------- | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| **01 Action**        | `Label_<replace_with_your_own_real_ID>` | Emails requiring your direct action/response                                                                     |
| **00 Action - Cust** | `Label_<replace_with_your_own_real_ID>` | Customer-related emails requiring action                                                                         |
| **10 Waiting For**   | `Label_<replace_with_your_own_real_ID>` | Emails where you're waiting for someone else's response                                                          |
| **05 Snoozed**       | `Label_<replace_with_your_own_real_ID>` | Deferred items to revisit later. Apply this label, then tell user to snooze in Gmail UI for the reminder timing. |

## Archive Labels

Use these for emails that should be archived/organized:

| Label                     | ID                                      | When to Use                                                                                                                                                                                                                                                                                                  |
| ------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Customers**             | `Label_<replace_with_your_own_real_ID>` | Customer communications, support, feedback                                                                                                                                                                                                                                                                   |
| **Sales**                 | `Label_<replace_with_your_own_real_ID>` | Sales inquiries, leads, deals                                                                                                                                                                                                                                                                                |
| **Investors**             | `Label_<replace_with_your_own_real_ID>` | Investor communications, updates                                                                                                                                                                                                                                                                             |
| **Fundraising**           | `Label_<replace_with_your_own_real_ID>` | Fundraising-related emails                                                                                                                                                                                                                                                                                   |
| **Hiring**                | `Label_<replace_with_your_own_real_ID>` | Recruiting, job postings                                                                                                                                                                                                                                                                                     |
| **Hiring Applications**   | `Label_<replace_with_your_own_real_ID>` | Job applications received                                                                                                                                                                                                                                                                                    |
| **Employees**             | `Label_<replace_with_your_own_real_ID>` | Internal employee communications                                                                                                                                                                                                                                                                             |
| **Payroll**               | `Label_<replace_with_your_own_real_ID>` | Payroll, compensation                                                                                                                                                                                                                                                                                        |
| **Benefits**              | `Label_<replace_with_your_own_real_ID>` | Employee benefits, insurance, 401k                                                                                                                                                                                                                                                                           |
| **HR**                    | `Label_<replace_with_your_own_real_ID>` | HR policies, general HR                                                                                                                                                                                                                                                                                      |
| **Legal**                 | `Label_<replace_with_your_own_real_ID>` | Legal matters, contracts                                                                                                                                                                                                                                                                                     |
| **Financial**             | `Label_<replace_with_your_own_real_ID>` | Financial statements, banking                                                                                                                                                                                                                                                                                |
| **Taxes and Accounting**  | `Label_<replace_with_your_own_real_ID>` | Tax documents, accounting                                                                                                                                                                                                                                                                                    |
| **Receipts and Expenses** | `Label_<replace_with_your_own_real_ID>` | Purchase receipts, invoices, expense reports                                                                                                                                                                                                                                                                 |
| **Eng and Product**       | `Label_<replace_with_your_own_real_ID>` | Engineering, product discussions                                                                                                                                                                                                                                                                             |
| **DevOps**                | `Label_<replace_with_your_own_real_ID>` | Infrastructure, deployments                                                                                                                                                                                                                                                                                  |
| **Security**              | `Label_<replace_with_your_own_real_ID>` | Security alerts, vulnerabilities                                                                                                                                                                                                                                                                             |
| **Marketing**             | `Label_<replace_with_your_own_real_ID>` | Marketing campaigns, analytics                                                                                                                                                                                                                                                                               |
| **Partnerships**          | `Label_<replace_with_your_own_real_ID>` | Partner communications                                                                                                                                                                                                                                                                                       |
| **Introductions**         | `Label_<replace_with_your_own_real_ID>` | Professional introductions                                                                                                                                                                                                                                                                                   |
| **Events**                | `Label_<replace_with_your_own_real_ID>` | Event invitations, conferences                                                                                                                                                                                                                                                                               |
| **Newsletters**           | `Label_<replace_with_your_own_real_ID>` | Newsletter subscriptions I explicitly signed up for. Emails from newsletter platforms like Substack or Beehiiv are **Email Spam** unless from a known subscription.                                                                                                                                          |
| **Notifications**         | `Label_<replace_with_your_own_real_ID>` | System notifications, alerts                                                                                                                                                                                                                                                                                 |
| **Signups**               | `Label_<replace_with_your_own_real_ID>` | Service signups, welcome emails                                                                                                                                                                                                                                                                              |
| **Vendors**               | `Label_<replace_with_your_own_real_ID>` | Non-financial emails from specific people (use Receipts and Expenses for invoices).                                                                                                                                                                                                                          |
| **External Help**         | `Label_<replace_with_your_own_real_ID>` | Customer support threads I have with external vendors. Use this once the support thread is resolved or no longer needs my action.                                                                                                                                                                            |
| **Meetings**              | `Label_<replace_with_your_own_real_ID>` | Calendar, meeting invites                                                                                                                                                                                                                                                                                    |
| **Linear**                | `Label_<replace_with_your_own_real_ID>` | Linear issue notifications                                                                                                                                                                                                                                                                                   |
| **Bugsnag**               | `Label_<replace_with_your_own_real_ID>` | Bugsnag error notifications                                                                                                                                                                                                                                                                                  |
| **On Call**               | `Label_<replace_with_your_own_real_ID>` | PagerDuty, on-call alerts                                                                                                                                                                                                                                                                                    |
| **Vanta**                 | `Label_<replace_with_your_own_real_ID>` | Emails from Vanta (compliance platform)                                                                                                                                                                                                                                                                      |
| **SEO Audit**             | `Label_<replace_with_your_own_real_ID>` | Site audit reports from Ahrefs, Semrush, and other SEO tools                                                                                                                                                                                                                                                 |
| **Gov**                   | `Label_<replace_with_your_own_real_ID>` | Government filings, annual reports, state agency correspondence                                                                                                                                                                                                                                              |
| **Testing**               | `Label_<replace_with_your_own_real_ID>` | Internal testing, sync issue reports from Whalesync                                                                                                                                                                                                                                                          |
| **Friends**               | `Label_<replace_with_your_own_real_ID>` | Personal/friend emails                                                                                                                                                                                                                                                                                       |
| **Other**                 | `Label_<replace_with_your_own_real_ID>` | Doesn't fit other categories                                                                                                                                                                                                                                                                                 |
| **Email Spam**            | `Label_<replace_with_your_own_real_ID>` | Spam that got through filters. This includes collaboration requests, link sharing, press placements, hiring and consultant outreach, podcast requests, unsolicited investment/funding requests, and unsolicited newsletters. Emails from newsletter platforms (Substack, Beehiiv, etc.) are spam by default. |

## Classification Guidelines

1. **Never spam if replied**: If I have replied in the email thread, it is NOT spam. Classify based on content.
2. **Priority**: Check if email needs action first → use Action labels
3. **Waiting**: If you sent something and this is a follow-up you're tracking → Waiting For
4. **Customer**: Any customer communication → Action - Cust or Customers
5. **Categorize**: Match to the most specific archive label
6. **Default**: If unclear, use "Other"

## Whitelisted Companies

Emails from these companies are NEVER spam. Classify based on content:

- Webflow (`*@webflow.com`, `*@contact.webflow.com`)
- YC (`*@ycombinator.com`) — Investors, not spam

## Sender-Based Rules

Common senders and their labels:

| Sender Pattern                        | Label         |
| ------------------------------------- | ------------- |
| `*@linear.app`                        | Linear        |
| `*@vanta.com`                         | Vanta         |
| `*@bugsnag.com`                       | Bugsnag       |
| `*@pagerduty.com`                     | On Call       |
| `*@semrush.com`                       | SEO Audit     |
| `*Ahrefs*`                            | SEO Audit     |
| `noreply@*`, `no-reply@*`             | Notifications |
| `*@posthog.com`                       | Newsletters   |
| `*@substack.com`                      | Email Spam    |
| `*@beehiiv.com`                       | Email Spam    |
| `*@delaware.gov`                      | Gov           |
| `*@irs.gov`                           | Gov           |
| `*@messages.dhs.gov`, E-Verify        | Gov           |
| `*@updates.linear.app` (login alerts) | Notifications |

## Processing Unread Emails

When asked to label unread emails:

1. Search for `is:unread in:inbox`
2. Read each email's subject, sender, and snippet
3. Apply the appropriate label based on the rules above
4. Do NOT mark as read (user will review)
5. Report what labels were applied

## Example Classification

```
Email: "Your Stripe payout has been sent"
From: notifications@stripe.com
→ Label: Receipts and Expenses (financial notification)

Email: "RE: Integration question"
From: john@iamacustomer.com
→ Label: 00 Action - Cust (customer needs response)

Email: "2025 Wrap Up - Community Update"
From: avalanchevc@substack.com
→ Label: Email Spam (unsolicited Substack newsletter)

Email: "WA OSOS Annual Report"
From: notifications@sos.wa.gov
→ Label: Gov (state government filing)
```

## Drafting Rules

When drafting email replies:

1. Never use emdashes. Use commas, periods, or semicolons instead.
