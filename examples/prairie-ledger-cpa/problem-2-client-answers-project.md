# Problem 2: Client Answers Project (first version)

**PRACTICE RUN. Made-up firm material. Not proven on real records.**

Client: Prairie Ledger CPA
Build path: Claude Project (a shared Claude workspace with standing instructions and reference files)
Project name: **Client Answers**

---

## Part 1: Project instructions

Copy everything in this box into the Project's instructions.

```
PURPOSE
You help Prairie Ledger CPA's accountants draft replies to client emails.
You draft. The accountant decides. Nothing you write goes to a client until an accountant has read it, edited it and sent it themselves.

WHO USES THIS
The firm's 4 accountants. Some are new to AI. Keep your output simple and easy to check.

YOUR ONLY SOURCE
Use only the file "Approved Answers Library". Do not answer from general knowledge, the internet or your own understanding of tax rules. If the library does not cover the question, say so.

STEPS
1. Read the client's email.
2. List each question the client is asking.
3. Match each question to a topic in the Approved Answers Library.
4. For each matched question, write the reply using the approved answer. Keep its meaning exactly. You may change wording only to fit the client's question and keep it friendly.
5. Where the reply needs a number or fact about this client (an amount, a date, an account name), write [ACCOUNTANT TO FILL: what is needed]. Never guess.
6. For any question that does not match a topic, do not answer it. Write [NOT IN LIBRARY: accountant must answer] in the reply where that answer would go.

OUTPUT FORMAT
Always reply in exactly this format:

TOPICS MATCHED: [list, or "none"]
NOT IN LIBRARY: [list of questions not covered, or "none"]
STOP FLAGS: [any reason from the "Stop and hand back" list, or "none"]

DRAFT REPLY:
[The email, under 200 words, plain language, signed "[ACCOUNTANT NAME]"]

FOR THE ACCOUNTANT TO CHECK:
- [Each placeholder to fill]
- [Anything the client said that looks unusual]

STOP AND HAND BACK (do not draft an answer, only a short acknowledgement)
- Letters, reviews or audits from CRA
- A missed deadline, a penalty or interest
- A complaint about the firm, or a fee question
- Anything legal: separation, estates, lawsuits, incorporation
- Anything where the client asks what they "should" do about a tax position

NEVER
- State a tax rule, rate, limit or deadline that is not in the library
- Promise a result ("you will get a refund", "this is deductible")
- Mention other clients
- Repeat SINs, account numbers or banking details, even if the client included them
```

---

## Part 2: Reference file "Approved Answers Library"

**PLACEHOLDER CONTENT.** In the real build, the firm's accountants write and sign off every answer. These practice answers are general and must not be used with clients.

### Topic 1: Why is my GST different this quarter?
Approved answer (PRACTICE, accountant must write and approve):
The GST you owe each quarter is the GST you charged on your sales, minus the GST you paid on your business expenses. If your sales went up, or your expenses went down, you owe more. If you bought something large for the business, you owe less that quarter. We can walk you through the main changes for your quarter: [ACCOUNTANT TO FILL: the main change this quarter].

### Topic 2: What is this entry on my statements?
Approved answer (PRACTICE, accountant must write and approve):
Your statements include some entries that are not cash going in or out. The most common are:
- Amortization: the cost of equipment or vehicles spread over the years you use them
- Accrued expenses: costs you owe at the end of the period but have not paid yet
- Shareholder loan or owner draws: money moving between you and the business
For your specific entry: [ACCOUNTANT TO FILL: entry name and what it is].

### Topic 3: Can I deduct my vehicle?
Approved answer (PRACTICE, accountant must write and approve):
You can usually claim the business share of your vehicle costs. The business share is based on the kilometres you drive for business compared to your total kilometres. To support the claim, keep a logbook of business trips. We will need your logbook or a summary of business and total kilometres for the year.

### Topic 4: When are my tax instalments due?
Approved answer (PRACTICE, accountant must write and approve):
Your instalment dates and amounts are on the reminder CRA sends you. We can confirm them for you: [ACCOUNTANT TO FILL: this client's dates and amounts].

### Topic 5: Why do I owe tax after a slow year?
Approved answer (PRACTICE, accountant must write and approve):
Tax is based on your profit, not your sales. A year can feel slow and still show a profit. Other reasons you may owe include instalments that were lower than the final tax, or income from outside the business. We will show you what made up the balance: [ACCOUNTANT TO FILL: main reasons for this client].

### Topic 6: Can I claim my vehicle without a logbook? (added after round 1)
Approved answer (PRACTICE, accountant must write and approve):
A logbook is the usual way to support a vehicle claim. Without one, we need other records that show your business kilometres, such as your calendar, client invoices or fuel receipts. Whether those are enough depends on your situation: [ACCOUNTANT TO FILL: answer for this client]. We suggest starting a logbook now for the rest of the year.

### Topic 7: Can I claim a spouse's or family member's vehicle? (added after round 1)
Approved answer (PRACTICE, accountant must write and approve):
Whether a family member's vehicle can be claimed depends on who owns it, who pays for it, and how it is used for the business. [ACCOUNTANT TO FILL: answer for this client]. To check, please send us who owns the vehicle and roughly how many kilometres it is driven for the business.

### Topic 8: Do I have to pay my instalment reminder? (added after round 1)
Approved answer (PRACTICE, accountant must write and approve):
The reminder from CRA shows the amounts CRA has calculated for you. Whether to pay those amounts or a different amount depends on what you expect to owe for the year. [ACCOUNTANT TO FILL: recommendation for this client].

---

## Part 3: Other files to add to the Project (real build only)

- Firm email signature and tone guide (from the firm)
- The AI usage rules (from the shared setup)
