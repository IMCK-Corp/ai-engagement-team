# Problem 3: Monthly Coding Check, Test Plan and Answer Key

**PRACTICE RUN. Made-up records. Not proven on real records.**

Written before any test was run. **The skill never sees this file.**

---

## The tests

| # | Test | How a person checks it | Pass rate |
|---|---|---|---|
| T1 | Planted errors caught | Compare the report's flags to the answer key below | At least 9 of 11 (version 2: the proposal's 80% bar, with error #11 added) |
| T2 | False alarms per client | Count flags that are not a planted error and not the "needs information" record | No more than 10 per client (from proposal) |
| T3 | Nothing is changed, only flagged | Report uses "may be" wording and no transaction is recoded | 3 of 3 clients |
| T4 | Hard case, unusual record: a legitimate new payee is not flagged as an error | Calgary Trade Show (Client A) appears only under "New payees" | 1 of 1 |
| T5 | Hard case, missing information: the unclear record goes to "Needs information" with no guessed account | POS PURCHASE 4471 (Client B) | 1 of 1 |
| T6 | Every reason can be checked in under a minute | Bookkeeper reads each reason | All flags |
| T7 | Hard case, large purchase with no memo goes to "Needs information" | Emco Supply $5,200, October 29 (Client A) | 1 of 1 (added in version 2) |

A single failure on T3, T4 or T5 means fix the skill and rerun all 3 clients.

**Pass rate check (new Value Analyst rule):** T1 and T2 count only the planted errors and false alarms. The two hard cases are tested separately in T4 and T5, so every pass rate can be met.

---

## Answer key: the 10 planted errors

| # | Client | Date | Name | Amount | Coded to | Should be | Check that should catch it |
|---|---|---|---|---|---|---|---|
| 1 | A | Oct 10 | Home Depot | 412.18 | Meals & Entertainment | Job Materials | C1 |
| 2 | A | Oct 9 | Ridgid Tool Supply | 4,850.00 | Small Tools | Equipment (asset) | C2 (payee is usually Small Tools, so C1 alone would miss it) |
| 3 | A | Oct 15 | Receiver General | 3,215.00 | Office Expense | GST/HST Payable | C3 and C1 |
| 4 | A | Oct 6 | Telus Mobility (second entry) | 148.62 | Telephone & Internet | Delete duplicate | C6 |
| 5 | B | Oct 9 | Sysco | 2,340.55 | Repairs & Maintenance | Cost of Goods Sold, Food | C1 |
| 6 | B | Oct 12 | Transfer to J. Nguyen | 2,000.00 | Wages | Shareholder Loan | C4 and C1 |
| 7 | B | Oct 1 | Square | 6,812.40 (in) | Supplies | Sales | C5 and C1 |
| 8 | C | Oct 3 | Netflix | 20.99 | Office Expense | Owner Draws (personal) | C7 |
| 9 | C | Oct 11 | Real Canadian Superstore | 186.43 | Meals & Entertainment | Owner Draws (personal) | C7 |
| 10 | C | Oct 7 | Intact Insurance | 1,236.00 | Rent | Insurance | C1 |
| 11 | A | Oct 23 | Home Depot | 3,000.00 | Job Materials | Equipment (asset): a generator | C9 (usual account is Job Materials and memo is vague, so C1 and C2 miss it). Added in version 2. |

## Hard cases

| Client | Date | Name | Amount | Expected |
|---|---|---|---|---|
| A | Oct 18 | Calgary Trade Show | 650.00 | New payee, correctly coded. Listed under "New payees" only. Not a flag. |
| B | Oct 18 | POS PURCHASE 4471 | 214.36 | "Needs information." Ask the client what it was. No guessed account. |
| A | Oct 29 | Emco Supply (no memo) | 5,200.00 | "Needs information" (C8, memo rule). Not flagged by C9, because Emco orders up to $5,450 are normal. Added in version 2. |

## Traps for false alarms

These are correct, but a careless check might flag them:
- Client A: Ridgid Tool Supply's usual account is Small Tools, so error 2 tests whether C2 works when C1 does not fire.
- Client A: Emco Supply at $1,128.40 is under the $1,500 threshold. Should not be flagged by C2.
- Client C: Intact annual policy at $1,236 is under the threshold. Should be flagged by C1 only, not C2.
- Client C: Shaw "home internet, business share" looks personal but is a normal business share. Should not be flagged.
- Client C: Marriott Vancouver vs "Marriott" in the guide: same payee. Should not be flagged as new.
