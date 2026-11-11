# Problem 3: Monthly Coding Check, Test Log (Round 1)

**PRACTICE RUN. Made-up records. Not proven on real records.**
**Run and graded by Claude.** Claude also made up the planted errors, so this test is weaker than one using real past errors.

Skill version: first version
Date: November 11, 2026
Transactions checked: 55 (Client A 21, Client B 19, Client C 15)

---

## Results by client

### Client A: Ridgeline Plumbing Ltd.

| Flag | Name | Amount | Check | Planted error? |
|---|---|---|---|---|
| 1 | Receiver General | 3,215.00 | C3, C1 | Yes (#3) |
| 2 | Ridgid Tool Supply | 4,850.00 | C2 | Yes (#2) |
| 3 | Home Depot | 412.18 | C1 | Yes (#1) |
| 4 | Telus Mobility (second entry) | 148.62 | C6 | Yes (#4) |

New payees: Calgary Trade Show, listed for information only. **T4 pass.**
False alarms: 0

### Client B: Prairie Rose Café Inc.

| Flag | Name | Amount | Check | Planted error? |
|---|---|---|---|---|
| 1 | Square (Oct 1) | 6,812.40 in | C5, C1 | Yes (#7) |
| 2 | Sysco (Oct 9) | 2,340.55 | C1, C2 | Yes (#5) |
| 3 | Sysco (Oct 21) | 2,212.10 | C2 | **No: false alarm** |
| 4 | Sysco (Oct 2) | 2,104.80 | C2 | **No: false alarm** |
| 5 | Transfer to J. Nguyen | 2,000.00 | C4, C1 | Yes (#6) |

Needs information: POS PURCHASE 4471, $214.36. No account guessed. Asks the client what it was. **T5 pass.**
False alarms: 2

### Client C: Kowalski Consulting

| Flag | Name | Amount | Check | Planted error? |
|---|---|---|---|---|
| 1 | Intact Insurance | 1,236.00 | C1 | Yes (#10) |
| 2 | Real Canadian Superstore | 186.43 | C7 | Yes (#9) |
| 3 | Netflix | 20.99 | C7 | Yes (#8) |

False alarms: 0
Traps passed: Shaw "home internet, business share" not flagged. Marriott Vancouver matched to Marriott. Intact flagged by C1 only, not C2.

---

## Results by test

| Test | Pass rate needed | Result | Pass/Fail |
|---|---|---|---|
| T1: Planted errors caught | At least 8 of 10 | 10 of 10 | Pass |
| T2: False alarms per client | No more than 10 | A: 0, B: 2, C: 0 | Pass |
| T3: Nothing changed, only flagged | 3 of 3 clients | 3 of 3 | Pass |
| T4: Legitimate new payee not flagged | 1 of 1 | 1 of 1 | Pass |
| T5: Unclear record sent to "Needs information" | 1 of 1 | 1 of 1 | Pass |
| T6: Each reason checkable in under a minute | All flags | 12 of 12 | Pass |

**Overall: 6 of 6 tests passed in this practice run.**

---

## Problems found, even though the tests passed

**1. Check C2 (large purchase) is too broad.** It flagged two normal Sysco food orders because they were over $1,500. Food bought for resale is not equipment. A café with 4 large food orders a month would get 4 false alarms every month. Bookkeepers will stop trusting a check that cries wolf.
- **Proposed fix:** apply C2 only when the payee's usual account is not Cost of Goods Sold or Job Materials, or when the memo describes equipment, a tool, a vehicle or furniture.

**2. Near miss on C7 (possibly personal).** LinkedIn "Premium subscription" (Client C) was not flagged, because the payee guide shows it as Advertising 3 times. That is correct, but the word "subscription" matches the firm's personal list. A client with no payee guide could see a false alarm here.
- **Proposed fix:** none needed yet. Add it to the watch list for real testing.

---

## Round 2: after the C2 fix (desk check)

C2 was narrowed so regular supplier orders for resale or job materials are not flagged. Instead of a full rerun, each C2-related transaction was rechecked against the new rule, because the fix only changes C2.

| Transaction | Round 1 | Round 2 | Why |
|---|---|---|---|
| Ridgid Tool Supply 4,850.00 (error #2) | Flagged | **Still flagged** | Usual account is Small Tools (not COGS or Job Materials), and memo says "machine" |
| Sysco 2,340.55 (error #5) | Flagged (C1, C2) | **Still flagged** (C1 only) | Payee coded differently than usual |
| Sysco 2,212.10 | False alarm | **Not flagged** | Usual account is Cost of Goods Sold |
| Sysco 2,104.80 | False alarm | **Not flagged** | Usual account is Cost of Goods Sold |
| Emco Supply 1,128.40 | Not flagged | Not flagged | Under threshold |
| Intact 1,236.00 (error #10) | Flagged (C1) | Flagged (C1) | C2 does not apply |

**Round 2 result:** errors caught 10 of 10. False alarms: A 0, B 0, C 0. All 6 tests still pass.

**New blind spot created by the fix:** a large equipment purchase from a materials supplier (for example a $3,000 generator from Home Depot, coded to Job Materials, memo "Job 1192") would now be missed, because Home Depot is usually Job Materials and the memo does not describe equipment. **Add this as a test case when testing on real records.**

---

## Round 3: after adding C9 "unusually large for this payee" (full rerun)

**Changes since round 2:**
- New check C9: a purchase over $1,500 and more than 2 times the payee's largest amount in the last 3 months
- C8 extended: a purchase over $1,500 with a memo that does not say what was bought goes to "Needs information"
- Wording fix: "purchase" defined as a payment to a supplier. Rent, payroll, tax remittances and owner transfers are not purchases.
- Test data version 2: "Largest" column in each payee guide, plus 2 new Client A transactions
- New planted error #11 (Home Depot generator) and new hard case (Emco $5,200, no memo)
- T1 pass rate: at least 9 of 11. New test T7.

All 3 clients were rerun in full: 57 transactions.

### Client A: Ridgeline Plumbing Ltd.

| Flag | Name | Amount | Check | Planted error? |
|---|---|---|---|---|
| 1 | Ridgid Tool Supply | 4,850.00 | C2, C9 | Yes (#2) |
| 2 | Receiver General | 3,215.00 | C3, C1 | Yes (#3) |
| 3 | Home Depot (Oct 23) | 3,000.00 | C9, C8 | Yes (#11) |
| 4 | Home Depot (Oct 10) | 412.18 | C1 | Yes (#1) |
| 5 | Telus Mobility (second entry) | 148.62 | C6 | Yes (#4) |

Needs information: Emco Supply, $5,200, no memo. Not flagged by C9, because Emco orders up to $5,450 are normal. **T7 pass.**
New payees: Calgary Trade Show, for information only. **T4 pass.**
False alarms: 0

### Client B: Prairie Rose Café Inc.

Flags: Square $6,812.40 in (C5, C1, #7), Sysco $2,340.55 (C1, #5), Transfer to J. Nguyen $2,000 (C4, C1, #6).
The two normal Sysco orders were not flagged by C9: $2,212.10 and $2,104.80 are both under 2 x $2,418.30.
Needs information: POS PURCHASE 4471. **T5 pass.**
False alarms: 0

### Client C: Kowalski Consulting

Flags: Intact $1,236 (C1, #10), Superstore $186.43 (C7, #9), Netflix $20.99 (C7, #8).
ATB transfer of $3,000 with no memo: not flagged by the memo rule, because it is an owner transfer, not a purchase. Before the wording fix, this would have been a false alarm.
False alarms: 0

### Results by test

| Test | Pass rate needed | Result | Pass/Fail |
|---|---|---|---|
| T1: Planted errors caught | At least 9 of 11 | 11 of 11 | Pass |
| T2: False alarms per client | No more than 10 | A: 0, B: 0, C: 0 | Pass |
| T3: Nothing changed, only flagged | 3 of 3 clients | 3 of 3 | Pass |
| T4: Legitimate new payee not flagged | 1 of 1 | 1 of 1 | Pass |
| T5: Unclear record sent to "Needs information" | 1 of 1 | 1 of 1 | Pass |
| T6: Each reason checkable in under a minute | All flags | 11 of 11 | Pass |
| T7: Large purchase with no memo sent to "Needs information" | 1 of 1 | 1 of 1 | Pass |

**Overall: 7 of 7 tests passed in this practice run.**

### What still gets through

- **Equipment from a supplier where large orders are normal, with a memo that sounds like materials.** For example, a $5,000 machine from Emco with the memo "Job 1195 pipe." No check based on numbers can catch this. The memo rule depends on bookkeepers writing honest memos. The year-end review stays as the final safety net.
- **The first 3 months of a new client**, before there is a payee guide. C1 and C9 cannot run. The skill says so in the report.

---

## Sample report: Client B (round 1)

```
CODING CHECK: Prairie Rose Café Inc., October 2026
Transactions checked: 19
Flags: 5

FLAGS
| # | Date   | Name                 | Amount       | Coded to                | Possibly should be       | Check  | Reason |
| 1 | Oct 1  | Square               | 6,812.40 in  | Supplies                | Sales                    | C5, C1 | Money in is coded to an expense account. Square deposits are usually Sales (13 times). |
| 2 | Oct 9  | Sysco                | 2,340.55     | Repairs & Maintenance   | Cost of Goods Sold, Food | C1, C2 | Sysco is usually Cost of Goods Sold, Food (9 times). |
| 3 | Oct 21 | Sysco                | 2,212.10     | Cost of Goods Sold, Food| Equipment?               | C2     | Over the $1,500 threshold and coded to an expense. |
| 4 | Oct 2  | Sysco                | 2,104.80     | Cost of Goods Sold, Food| Equipment?               | C2     | Over the $1,500 threshold and coded to an expense. |
| 5 | Oct 12 | Transfer to J. Nguyen| 2,000.00     | Wages                   | Shareholder Loan         | C4, C1 | Transfers to the owner are usually Shareholder Loan (3 times). |

NEEDS INFORMATION
| Date   | Name              | Amount | Coded to             | What to ask the client |
| Oct 18 | POS PURCHASE 4471 | 214.36 | Uncategorized Expense| What was this purchase, and where was it made? |

NEW PAYEES (for information only)
none

NOTES FOR THE BOOKKEEPER
- These may be miscoded. Nothing has been changed.
```

Flags 3 and 4 are the false alarms described above.
