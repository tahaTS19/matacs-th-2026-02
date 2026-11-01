# Proposal Triage System – Questions & Answers

## Question #1

**Answer:**

The language analysis part, where we have to read the proposal, compare it to criterion and decide what score to give it uses Ai, since that is the part where we reduce human effort of reading each proposal and ranking it through Ai integration.

Extracting text from pdf, fetching rules from where admin stores them (database or else) and final weight and score calculations, we will use backend code and the fixed rules that the admin defined

**Why draw the line ?**

As backend code can easily do calculations and it is also more reliable as compared to Ai (Ai might make an error in calculating). Extracting text at backend so we dont get additional ai usage cost, and followed by human review we can verify it.

Fetching criteria from source so ai knows what to check against, and doesnt make up stuff.

---

## Question #2

**Answer:**

We can not remove this probability completely as slight variation in scoring is always expected, however we can reduce it by using a standardized well engineered prompt, a fixed and clear set of criteria.

---

## Question #3

**Answer:**

A human enters the loop to review what ai did, and give a final verdict or approval for it.

**Instances in our design:**

1. Human review after the final ranking: See why a proposal was ranked, flagged, ineligible. Approve it or override it, for e.g: Proposal D was flagged for no timeline, reviewer adds a note in proposal for giving timeline score as it will be decided after inspection

2. Human reviews text extracted by backend, costs time and effort but if ai processes wrong text and generates result on the basis of that it can be even more costly.

3. Human reviews if AI separated proposals correctly

---

## Question #4

**Answer:**

Check criteria before and after evaluating, if its the same, we are good. If changed, re evaluate against the new criteria.

Or if you mean admin modifying criteria after the ranking was approved:

Admin shall also notify if re evaluation against the new criteria is required, if yes, it will be done again, if no: leave it as it is.

---

## Question #5

**Answer:**

1. **Risk: Bad text extraction**

   **Fix:** Human Review

2. **Risk: Ai hallucinates criteria or information**

   **Fix:** Clear criteria and proposal text provided

3. **Risk: Incorrect weights assigned**

   **Fix:** Backend calculates weights

4. **Risk: Bad proposal separation**

   **Fix:** Human Review and approval