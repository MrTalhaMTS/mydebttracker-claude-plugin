---
name: record-repayment
description: Log a repayment in MyDebtTracker. Use when the user says someone paid them back, or that they paid back a loan, and wants it recorded.
---

# Record a repayment

1. Find the debt with `list_debts`. If more than one matches (same person, several debts), ask which one.
2. Confirm with the user before writing: the person, the debt, the amount, the date, and the balance that will remain.
3. Only after a clear yes, call `record_payment` with `debt_id`, `amount`, and optionally `date` (YYYY-MM-DD), `method` and `notes`.
4. Report the remaining balance returned by the tool. If it reaches zero, say the debt is now cleared.

`record_payment` only adds a payment. It cannot edit or delete records, so if the user made a mistake, tell them to correct it in the MyDebtTracker app at https://mydebttracker.app.
