---
name: monthly-coding-check
description: Checks one bookkeeping client's monthly QuickBooks Online transactions for entries that look miscoded, and lists them for the bookkeeper to review. Use when a Prairie Ledger bookkeeper says "run the coding check" and provides a client's monthly transaction export and payee guide.
---

# Monthly Coding Check

**PRACTICE RUN. Built for Prairie Ledger CPA with made-up records. Not proven on real records.**

## What this skill does

You check one client's transactions for one month and list the ones that look miscoded. You never change anything. The bookkeeper reviews every flag and decides.

## What you need before starting

Ask for anything missing. Do not start without all three.

1. **This month's transactions** for one client, exported from QuickBooks Online. Columns: Date, Name, Memo, Money In, Money Out, Account.
2. **The client's payee guide:** each regular payee, the account it is usually coded to, and the largest single amount paid to it, from the last 3 months.
3. **The firm's coding rules** (the "Firm Coding Rules" file in this Project).

## Steps

1. Count the transactions. Confirm the client name and month with the bookkeeper.
2. Check every transaction against each check below, in order.
3. Write the report using the template below.
4. If you have more than 10 flags, show the 10 with the largest amounts and say how many more there are.

## The checks

| # | Check | Flag when |
|---|---|---|
| C1 | Payee coded differently than usual | A payee in the guide is coded to a different account this month |
| C2 | Large purchase coded as an expense | A single purchase is over the firm's capital threshold, is coded to an expense account, AND either (a) the payee is not usually coded to Cost of Goods Sold or Job Materials, or (b) the memo describes equipment, a tool, a machine, a vehicle, a computer or furniture. Regular supplier orders for resale or job materials are not flagged by C2. |
| C3 | GST payment coded as an expense | A payment to the Receiver General or CRA for GST is coded to anything other than GST/HST Payable |
| C4 | Owner money coded as a business expense | A transfer to the owner is coded to anything other than Shareholder Loan (corporation) or Owner Draws (sole proprietor) |
| C5 | Money in coded to an expense account | A Money In amount is coded to an expense account |
| C6 | Possible duplicate | Same payee and same amount within 3 days |
| C7 | Possibly personal | Payee or memo looks personal under the firm's rules (for example streaming, groceries, clothing) |
| C8 | Needs information | Coded to Uncategorized or Ask My Accountant, or the name and memo do not say what it was, or a purchase is over the firm's capital threshold and the memo does not say what was bought |
| C9 | Unusually large for this payee | A purchase (Money Out) is over the firm's capital threshold AND more than 2 times the largest amount paid to that payee in the last 3 months. It may be equipment coded as an expense. |

**"Purchase" means** a payment to a supplier for goods or services. Rent, payroll, tax remittances and transfers to the owner are not purchases, so C2, C9 and the memo rule in C8 do not apply to them. Those are covered by C1, C3 and C4.

**New payees** (not in the guide) are not errors on their own. List them under "New payees" for information, unless another check also applies.

## Report template

```
CODING CHECK: [Client name], [Month]
Transactions checked: [number]
Flags: [number]

FLAGS
| # | Date | Name | Amount | Coded to | Possibly should be | Check | Reason |

NEEDS INFORMATION
| Date | Name | Amount | Coded to | What to ask the client |

NEW PAYEES (for information only)
| Date | Name | Amount | Coded to |

NOTES FOR THE BOOKKEEPER
- Anything unusual that is not a flag
```

Write each reason in one plain sentence that a bookkeeper can check in under a minute. Example: "Home Depot is usually coded to Job Materials (14 times in 3 months)."

## Never

- Never change, delete or recode a transaction. Only flag.
- Never say a transaction "is" wrong. Say it "may be" miscoded and why.
- Never decide whether something personal is deductible. Flag it for the bookkeeper.
- Never guess an account for a "needs information" item. Say what to ask the client.
- Never include bank account numbers or card numbers in the report.

## Edge cases

- **A payee with two normal accounts** (for example Costco for supplies and for food): only flag if this month's account matches neither.
- **A refund** (Money In from a supplier): flag under C5 only if coded to an account the payee is never coded to.
- **No payee guide for a new client:** run checks C2 to C8 only, and say in the report that C1 and C9 were skipped. For C2, treat every payee as not usually coded to Cost of Goods Sold or Job Materials, so all large purchases are checked.
