---
name: repayment-plan
description: Plan how to repay or collect an interest-free debt in instalments. Use when the user wants a realistic schedule for a debt they owe or are owed.
---

# Interest-free repayment plan

1. Look up the debt with `list_debts` to get the remaining amount, currency and any due date.
2. Ask how much the person can pay each month, or by what date it should be cleared. Offer to work out the other.
3. Produce an equal-instalment schedule with dates. The total of the instalments must equal the remaining amount exactly, with any rounding in the last instalment.
4. Add no interest, fees or penalties. MyDebtTracker is for interest-free lending.
5. Offer to record each instalment later with the `record-repayment` skill. Do not record anything now.
