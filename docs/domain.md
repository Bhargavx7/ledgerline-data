# Payments domain

## Glossary
- **Authorization:** The customer’s bank approves and holds the amount, and no money moves yet
- **Capture:** 	The request to collect the authorized amount
- **Settlement:**  money moves from the customer’s bank to the processor
- **Refund:** The merchant sends money back from an earlier charge
- **Dispute:** The customer challenges a charge through their bank
- **Payout:** getting money from processor to merchants bank,
- **PaymentIntent vs. Charge:** The overall process of collecting payment vs. one attempt, and one PaymentIntent can have several Charges
- **Balance Transaction:** Records every balance change, with its source and fee, so finance can tally everything
- **Currency rule:** Amounts are integers in the smallest unit, and you divide by 10 to the power of the currency’s decimal places

## Lifecycle timeline
| Date | Event | Objects | Pending | Available | Ledgerline revenue |
|---|---|---|---|---|---|
| Mon, Nov 2 | Authorized and captured | PaymentIntent, Charge and Balance Transaction created | +$96.80 | $0 | +$3.20 fee |
| Wed, Nov 4 | Funds become available | Existing Balance Transaction changes from pending to available | −$96.80 | +$96.80 | None |
| Thu, Nov 5 | Payout to bank | Payout and Balance Transaction created | No change | −$96.80 | None |
| Mon, Nov 16 | Dispute opened | Dispute and Balance Transaction created | No change | −$115.00 | +$15 fee |
