---
name: debt-review
description: Review the user's MyDebtTracker ledger. Use when they ask what they owe, who owes them, what is overdue or due soon, or want a summary of their lending and borrowing.
---

# Debt review

Use the MyDebtTracker connector tools to answer from the user's real ledger. Never guess figures.

1. Call `get_debt_summary` for totals. Report each currency separately and never add currencies together.
2. Call `list_upcoming_dues` (default 30 days) for anything overdue or coming due. Put overdue items first.
3. Call `list_debts` only when the user asks about a specific person, type (`lent` or `borrowed`) or status.
4. Present a short result: what the user is owed, what they owe, the net position per currency, then the items needing action.
5. If asked, draft a polite reminder message for the user to send themselves. This plugin cannot send messages.

All debts in MyDebtTracker are interest free. Do not calculate or suggest interest.
