# Proposal: Document Reminders, Client Answers and Monthly Coding Checks

**PRACTICE CASE. Prairie Ledger CPA is a made-up firm. Every name and number is fictional.**

**For:** Dana and Greg, Prairie Ledger CPA, Red Deer
**Prepared by:** Colette Kenney
**Date:** November 11, 2026

Three problems cost the firm about $90,000 a year in staff time. This $6,500 fix is worth about $29,000 in the first year, so it pays for itself in under 3 months.

## The problem

Bookkeepers spend hours every month chasing the same clients for documents: "Every month it's the same people." Accountants write a fresh answer to the same client questions, and in tax season "we stop answering emails properly and clients get annoyed." Rushed month-end reviews let coding errors through, and they get fixed at year-end, when "fixing it then takes way longer."

## What it costs you today

| Problem | Per year | Source |
|---|---|---|
| 1. Bookkeepers chasing documents | $19,200 to $21,600 | Hours estimated by client, cost stated |
| 2. Accountants answering repeat client questions | $62,920 | Hours estimated by client, cost stated |
| 3. Coding errors fixed at year-end | $7,730 | Hours estimated by client, rates stated |
| **Total** | **$89,850 to $92,250** | |

These totals count staff time only. Extra clients and Saturday overtime are shown in the appendix as upside.

## What the fix is worth in the first year

| Problem | Share of the cost removed | First-year value |
|---|---|---|
| 1. Document chasing | 50% | $9,600 |
| 2. Repeat client questions | 25% | $15,730 |
| 3. Coding errors | 50% | $3,865 |
| **Total** | | **$29,195** |

We used conservative shares. Some clients will still need a phone call, and an accountant reviews every client answer before it goes out.

## What we will do

**First, for everyone (before any real client records are used)**

1. Firm Claude accounts, so staff stop using personal ChatGPT accounts with client information.
2. One page of plain AI usage rules, and a 30-minute walkthrough for all staff.

**Problem 1: Document chasing (Karbon setup, no AI needed)**

3. Turn on Karbon's automatic reminders for all monthly bookkeeping work.
4. Set up a Karbon view of clients still missing documents, so bookkeepers phone only the ones who need it.
5. Training for the bookkeepers.

**Problem 2: Repeat client questions (Claude Project)**

6. A library of approved answers for the 5 most common topics, written and signed off by the firm's accountants.
7. A Claude Project that drafts replies from that library. An accountant reviews and edits every reply before it is sent.
8. Testing on 20 real past client emails, and training for the accountants before tax season.

**Problem 3: Coding errors (tested prototype)**

9. A monthly coding check. The bookkeeper exports a client's transactions from QuickBooks Online, runs the check, and reviews the entries it flags.
10. Testing on 3 clients' real records before it goes live, and training for the bookkeepers.

## What is not included

- Phoning clients
- Tax advice. The firm's accountants write and approve every answer.
- Changes to the QuickBooks Online setup or chart of accounts
- Running the coding check automatically for every client without a person. That would be a separate, larger build.
- Custom software or automatic connections between Karbon, QuickBooks Online and Claude
- Software subscriptions
- Support after February 26

## What success looks like

**Tests before anything goes live (pass rates)**

| Problem | Test | Pass rate |
|---|---|---|
| 1. Document chasing | Automatic reminders scheduled for monthly bookkeeping clients | 100% of clients |
| 2. Client questions | Drafts that need only light edits | At least 16 of 20 |
| 2. Client questions | Drafts that state a tax rule not in the approved answers | 0 of 20 |
| 3. Coding errors | Known errors from last year caught | At least 8 of 10 |
| 3. Coding errors | False alarms per client per month | No more than 10 |

**Results after go-live**

- Time spent chasing documents drops from about 40 hours a month to 20 hours or less.
- Accountant time on client questions drops by at least a quarter in February.
- More clients are closed by the 15th than today's "about half."
- Year-end cleanup is at least halved, measured at the next year-end.
- All staff use firm AI accounts only.

## Investment

**$6,500 fixed price, plus GST.** Half on approval, half at handover.

Why this price: the fix is worth about $29,195 in the first year, and the price is about 22% of that. It pays for itself in under 3 months.

## Timeline

- **By November 27:** approval
- **Week of November 30:** firm accounts, usage rules, Karbon reminders on
- **December:** answer library and Claude Project built
- **January:** coding check built and tested, accountant training
- **By January 29:** handover, before tax season
- **To February 26:** support, then a one-page results report

## What we need from you

- Admin access to Karbon
- Firm Claude accounts for staff
- **20 past client emails with replies, names removed**, used only for testing
- The accountants' approved answers for the 5 common topics
- QuickBooks Online exports and last year's known coding errors for 3 test clients
- Written permission to use these records for testing
- One contact person, and about 2 hours of training time from each bookkeeper and accountant

---

## Appendix: calculations

**Problem 1:** 40 hrs/month x 12 x $40 = $19,200. Fix value: 240 hrs x $40 = $9,600.

**Problem 2:** (4 hrs/week x 4 accountants x 39 weeks) + (10 hrs/week x 4 accountants x 13 weeks) = 1,144 hrs. 1,144 x $55 = $62,920. Fix value: 286 hrs x $55 = $15,730.

**Problem 3:** (40 x $55) + (20 x $250) + (5 x $40) + (6 x $55) = $7,730. Fix value: 50% = $3,865.

**Payback:** $29,195 / 12 = $2,433 a month. $6,500 / $2,433 = 2.7 months.

**Note added after prototype testing:** the pass rate of 16 of 20 for client answers could not be met by design, because 6 of the 20 test emails are hard cases the AI must not answer. It was changed to 12 of 14 normal emails, with the client's agreement. The Value Analyst skill was then updated to check every pass rate before it goes into a proposal.
