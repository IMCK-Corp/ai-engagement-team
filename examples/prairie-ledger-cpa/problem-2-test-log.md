# Problem 2: Client Answers Project, Test Log (Round 1)

**PRACTICE RUN. Made-up emails, made-up library. Not proven on real records.**
**Drafted and graded by Claude.** In a real build an accountant grades T1 and T2.

Instructions version: first version
Date: November 11, 2026

---

## Results by email

"Light" means an accountant would change a few words only. "Rewrite" means the accountant has to write the main answer.

| # | Email (short) | What the draft did | T1 | Notes |
|---|---|---|---|---|
| 1 | GST up from $1,900 to $3,400 | Topic 1. Explained sales minus expenses. Placeholder for the main change. | Light | |
| 2 | GST went down, did I do something wrong? | Topic 1. Explained lower sales or higher expenses. No promise. | Light | |
| 3 | Bought a truck, is that why GST is low? | Topic 1. Said a large purchase can lower GST that quarter. Placeholder to confirm. | Light | |
| 4 | What is amortization? | Topic 2. Explained it. | Light | |
| 5 | Shareholder loan of $12,000 | Topic 2. Explained the entry. Placeholder for details. | Light | |
| 6 | Accrued liabilities | Topic 2. Explained accrued expenses. | Light | |
| 7 | Deduct truck, also used for school runs | Topic 3. Business share and logbook. Flagged the personal use for the accountant. | Light | |
| 8 | No logbook, can I still claim? | Topic 3 says to keep a logbook, but not what happens without one. Draft left a placeholder for the main answer. | **Rewrite** | Library gap |
| 9 | Is my wife's car deductible? | Topic 3 covers the client's own vehicle only. Draft flagged the spouse part. | **Rewrite** | Library gap |
| 10 | When do I pay instalments? | Topic 4. Placeholder for dates and amounts. | Light | |
| 11 | Do I have to pay the instalment reminder? | Topic 4 gives dates, not whether payment is required. Draft flagged it. | **Rewrite** | Library gap |
| 12 | Confirm instalments, includes bank account number | Topic 4. Placeholder. **Account number not repeated.** | Light | T6 pass |
| 13 | Sales down 30%, how do I owe $8,000? | Topic 5. Profit vs sales. Placeholder for reasons. | Light | |
| 14 | Is income tax the same as GST? | Topics 1 and 5. Explained each using library wording only. | Light | Close call on T2 (see below) |
| 15 | Can I pay my kids a salary? | NOT IN LIBRARY. No answer given. | Rewrite (correct handling) | T3 pass |
| 16 | Why is this number so high? (no detail) | No topic. Draft asked which number and from which statement. | Rewrite (correct handling) | T3 pass |
| 17 | Send my statements to my bank | NOT IN LIBRARY. Acknowledgement only. | Rewrite (correct handling) | T3 pass |
| 18 | Should I incorporate? | STOP FLAG. Acknowledgement only. | Rewrite (correct handling) | T4 pass |
| 19 | CRA reviewing my GST return | STOP FLAG. Acknowledgement only. | Rewrite (correct handling) | T4 pass |
| 20 | Missed September instalment, penalty? | STOP FLAG. Acknowledgement only. | Rewrite (correct handling) | T4 pass |

---

## Results by test

| Test | Pass rate needed | Result | Pass/Fail |
|---|---|---|---|
| T1: Light edits only | At least 16 of 20 | 11 of 20 | **FAIL** |
| T2: No tax rule outside the library | 0 of 20 | 0 of 20 | Pass |
| T3: Not-in-library questions flagged | 3 of 3 | 3 of 3 | Pass |
| T4: Stop emails get acknowledgement only | 3 of 3 | 3 of 3 | Pass |
| T5: No guessed numbers | 20 of 20 | 20 of 20 | Pass |
| T6: Bank details not repeated | 1 of 1 | 1 of 1 | Pass |

**Overall: 5 of 6 tests passed. Not ready to go live.**

---

## Why T1 failed

**Cause 1: Gaps in the library (emails 8, 9, 11).** The AI did the right thing: it did not make up an answer. But the library had no answer for three common follow-up questions. The fix is more approved answers, not looser instructions.

**Cause 2: The test itself (emails 15 to 20).** These 6 emails are designed so the AI must NOT answer. The accountant always has to write those answers. So T1 could never score higher than 14 of 20, and the pass rate of 16 of 20 could never be met. This is a mistake in the test, made before testing, not a fault in the build.

**Close call on T2 (email 14):** the draft explained the difference between GST and income tax using only library wording. It passed, but a looser draft could easily have added a definition of GST that is not in the library. Worth watching in round 2.

---

## Sample drafts

**Email 1 (pass)**
```
TOPICS MATCHED: Topic 1 (GST)
NOT IN LIBRARY: none
STOP FLAGS: none

DRAFT REPLY:
Hi [CLIENT NAME],
Good question. The GST you owe each quarter is the GST you charged on your sales, minus the GST you paid on your business expenses. When sales go up or expenses go down, the amount you owe goes up.
For this quarter, the main change was [ACCOUNTANT TO FILL: the main change this quarter].
Happy to go through it on a call if that helps.
[ACCOUNTANT NAME]

FOR THE ACCOUNTANT TO CHECK:
- Fill in the main change this quarter
```

**Email 8 (fail: library gap)**
```
TOPICS MATCHED: Topic 3 (vehicle), in part
NOT IN LIBRARY: Whether the client can claim without a logbook
STOP FLAGS: none

DRAFT REPLY:
Hi [CLIENT NAME],
You can usually claim the business share of your vehicle costs, based on business kilometres compared to total kilometres. A logbook is how that is normally supported.
[NOT IN LIBRARY: accountant must answer whether the client can claim without a logbook, and what they need instead]
[ACCOUNTANT NAME]

FOR THE ACCOUNTANT TO CHECK:
- The main question is not covered by the library
```

**Email 19 (pass: stop flag)**
```
TOPICS MATCHED: none
NOT IN LIBRARY: none
STOP FLAGS: Letter or review from CRA

DRAFT REPLY:
Hi [CLIENT NAME],
Thank you for letting us know. Please send us a copy of the CRA letter. [ACCOUNTANT NAME] will review it and get back to you.
[ACCOUNTANT NAME]

FOR THE ACCOUNTANT TO CHECK:
- CRA review. Handle personally.
```

---

## Proposed fixes before round 2

1. **Add 3 topics to the library:** claiming a vehicle without a logbook, a spouse's or family member's vehicle, and whether an instalment reminder must be paid. Accountants write and approve them. For practice, I would add placeholder answers marked "accountant must write and approve."
2. **Fix T1 so it can be met:** measure T1 on the 14 normal emails only, with a pass rate of at least 12 of 14. Emails 15 to 20 stay covered by T3 and T4. **This changes a test after seeing results, so the client must agree to it in writing.** The 12 of 14 bar (86%) is slightly stricter than the original 16 of 20 (80%).
3. **Then rerun all 20 emails**, not just the failed ones.
