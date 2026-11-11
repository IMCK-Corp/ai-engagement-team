# BUILD RECORD: Document Reminders, Client Answers and Monthly Coding Checks

**PRACTICE RUN. Every test used made-up records. Nothing here is proven on real records.**

**Client:** Prairie Ledger CPA, Red Deer
**Build paths:** Karbon setup (Problem 1), Claude Project (Problem 2), Claude skill (Problem 3)
**Date:** November 11, 2026

---

## WHAT WAS BUILT

1. **Document reminders (Karbon, no AI).** A setup checklist that turns on Karbon's automatic client requests and reminders for monthly bookkeeping, and creates a "Call client" list for clients still missing documents after 5 reminders.
2. **Client Answers (Claude Project).** Drafts replies to client email questions using only the firm's approved answers. The accountant reviews, edits and sends every reply. CRA letters, missed deadlines, legal questions and "should I" tax questions get an acknowledgement only.
3. **Monthly Coding Check (Claude skill).** The bookkeeper gives it one client's monthly transactions and payee guide. It lists entries that may be miscoded, with a one-line reason for each. It never changes anything.

---

## HOW TO USE IT

**Document reminders**
1. Nothing to do each month. Karbon sends the requests and reminders.
2. Each month, check the "Call client" view and phone those clients.

**Client Answers**
1. Open the Client Answers Project in the firm's Claude workspace.
2. Paste the client's email. Remove any SIN, bank or card numbers first.
3. Read the draft. Fill in every [ACCOUNTANT TO FILL] placeholder.
4. Answer anything marked [NOT IN LIBRARY] or STOP FLAG yourself.
5. Copy the reply into Outlook and send it.
6. If the same new question comes up twice, ask for an approved answer to be added to the library.

**Monthly Coding Check**
1. In QuickBooks Online, export the client's transactions for the month, and the payee history for the last 3 months.
2. Open the firm's Claude workspace and say "run the coding check" for that client and month. Attach both files.
3. Review each flag. Recode in QuickBooks Online yourself if you agree.
4. Ask the client about each "Needs information" item.

---

## WHERE IT LIVES

| Piece | Where |
|---|---|
| Document reminders | Karbon: the monthly bookkeeping work template, and the saved "Call client" view |
| Client Answers | Firm Claude workspace: Project "Client Answers", with the file "Approved Answers Library" |
| Monthly Coding Check | Firm Claude workspace: skill "monthly-coding-check", with the file "Firm Coding Rules" |

Detailed files: problem-1-karbon-reminders-checklist.md, problem-2-client-answers-project.md, problem-3-coding-check-skill.md

---

## TEST LOG

| # | Piece | Test | Pass rate needed | Result | Pass/Fail | Notes |
|---|---|---|---|---|---|---|
| 1 | Reminders | Requests and reminders scheduled for monthly clients | 100% | Not run | Not run | Needs Karbon access |
| 2 | Client Answers | Light edits only (emails 1 to 14) | At least 12 of 14 | 14 of 14 | Pass | Round 2. Round 1 failed at 11 of 14 (library gaps). Bar changed from 16 of 20 after round 1, with user agreement. |
| 3 | Client Answers | No tax rule outside the library | 0 of 20 | 0 of 20 | Pass | |
| 4 | Client Answers | Out-of-library questions flagged | 3 of 3 | 3 of 3 | Pass | |
| 5 | Client Answers | Stop emails get acknowledgement only | 3 of 3 | 3 of 3 | Pass | |
| 6 | Client Answers | No guessed numbers | 20 of 20 | 20 of 20 | Pass | |
| 7 | Client Answers | Bank details not repeated | 1 of 1 | 1 of 1 | Pass | |
| 8 | Coding Check | Planted errors caught | At least 9 of 11 | 11 of 11 | Pass | Round 3, after adding the "unusually large for this payee" check |
| 9 | Coding Check | False alarms per client | No more than 10 | 0, 0, 0 | Pass | Round 1 had 2 false alarms (Sysco), fixed in round 2 |
| 10 | Coding Check | Nothing changed, only flagged | 3 of 3 | 3 of 3 | Pass | |
| 11 | Coding Check | Legitimate new payee not flagged | 1 of 1 | 1 of 1 | Pass | |
| 12 | Coding Check | Unclear record sent to "Needs information" | 1 of 1 | 1 of 1 | Pass | |
| 13 | Coding Check | Reasons checkable in under a minute | All | 11 of 11 | Pass | |
| 14 | Coding Check | Large purchase with no memo sent to "Needs information" | 1 of 1 | 1 of 1 | Pass | |

**Pass rate: 13 of 13 tests run passed. 1 test not run (needs Karbon access).**

All tests used made-up records. Claude wrote, ran and graded them, which is weaker than an accountant or bookkeeper grading real records.

---

## KNOWN LIMITS

- **Not proven on real records.** Before go-live, rerun every test with the firm's 20 real client emails and 3 clients' real transactions, graded by an accountant and a bookkeeper.
- **The answer library is placeholder content.** The firm's accountants must write and approve all 8 answers before use.
- **Client Answers can only be as good as the library.** New questions will keep appearing. An accountant answers them, and repeated ones are added to the library.
- **The coding check cannot catch equipment that looks like normal materials** (for example a machine bought from a pipe supplier with the memo "Job 1195 pipe"). The year-end review stays as the safety net.
- **A new client's first 3 months:** no payee guide yet, so 2 of the 9 checks cannot run. The report says so.
- **A person must always check:** every client reply before it is sent, every coding flag before anything is recoded, and every "Needs information" item.

---

## LATER LIST

Ideas that came up but are outside this scope. Raise any of these as a scope change through the Delivery Lead.

- Run the coding check automatically for all 90 clients each month (a production build for the AI Solutions Architect)
- Draft client replies directly inside Outlook, instead of copy and paste
- Connect Karbon, QuickBooks Online and Claude so files do not need exporting
- Hand Dana's review work to a senior accountant (a staffing decision, not an AI build)
- Track which library answers are used most, to guide what to add next
