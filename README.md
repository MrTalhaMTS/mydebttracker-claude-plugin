# MyDebtTracker for Claude

Ask Claude about the money you have lent and borrowed, using your own MyDebtTracker ledger. MyDebtTracker (https://mydebttracker.app) is an interest-free debt and loan tracker, so nothing here calculates interest.

## What it does

The plugin connects Claude to the MyDebtTracker remote MCP server at `https://mydebttracker.app/mcp` and adds four skills.

| Tool | What it does | Changes data? |
| --- | --- | --- |
| `get_debt_summary` | Totals per currency: owed to you, you owe, net, overdue count | No |
| `list_debts` | Your debts, filtered by lent or borrowed and by active or cleared | No |
| `list_upcoming_dues` | Overdue debts and those due in the next N days | No |
| `list_payments` | Recorded repayments, optionally for one debt | No |
| `record_payment` | Adds a repayment and lowers the debt's balance | Adds one payment |

No tool deletes or edits existing records, and no tool sends email or messages.

| Skill | Use it to |
| --- | --- |
| `debt-review` | Summarise what you owe, who owes you, and what is overdue |
| `record-repayment` | Log a repayment after confirming the details |
| `repayment-plan` | Build an interest-free instalment schedule |
| `zakat-on-debts` | Understand how lent and owed money relates to Zakat |

## Sign in and permissions

Adding the connector opens a MyDebtTracker sign-in (Google) and an Allow or Deny screen. The access you grant is a single `debts` scope: read your debts, borrowers, lenders, payments and due dates, and record a payment you ask for. It does not include Zakat records, attachments, billing or account settings. Family members with view-only access to a ledger cannot record payments. You can revoke access at any time from Claude's connector settings.

## Data handling

- The plugin has no scripts, hooks or local code. It runs nothing on your machine.
- Claude sends requests only to `https://mydebttracker.app`. No other service is contacted.
- Your ledger data is returned to Claude to answer your question. MyDebtTracker stores your data in Cloudflare D1 in your account and does not sell it. Access tokens are stored only as SHA-256 hashes and expire after one hour. Refresh tokens expire after 60 days and rotate on use.
- Not intended for people under 18.

Privacy policy: https://mydebttracker.app/privacy · Terms: https://mydebttracker.app/terms · Support: https://mydebttracker.app/contact

## Install

Once listed, open the Claude directory, find MyDebtTracker, and add it. You need a free MyDebtTracker account at https://mydebttracker.app.

## License

MIT. See `LICENSE`.
