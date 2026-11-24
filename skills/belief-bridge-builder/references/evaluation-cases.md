# Evaluation cases

16 labelled cases for checking whether the builder finds the missing plank. Run them before trusting it.

How to use: load `SKILL.md`, paste the pitch description, compare the plank verdicts and the named weakest plank against the expected column.

---

## 1. Straightforward

| # | Pitch | Missing plank |
|---|---|---|
| 1 | "Great demo, no customers yet, we are pre-launch." | 01 Evidence |
| 2 | "Twelve logos, strong numbers, no framing for what category this is." | 02 Analogy |
| 3 | "Strong proof from three retailers. Pitching a hospital." | 03 Proof Point |
| 4 | "Everything lands, champion says I love it, then nothing for six weeks." | 04 Transfer |
| 5 | "Named reference in their industry, their size, who will take a call, and a one-line summary they repeated back." | None. All four built |

## 2. Strong on three planks, still loses

The cases the skill exists for.

| # | Pitch | Expected | The tell |
|---|---|---|---|
| 6 | "We say it is the Salesforce of agentic AI. Buyer is a CFO who was burned on a CRM rollout." | 02 Analogy, actively harmful | A wrong analogy imports the last disappointment. Worse than no analogy |
| 7 | "Our proof point is a 50-person startup. Buyer is 6,000 people." | 03 Proof Point | Size mismatch is a mismatch even in the same industry |
| 8 | "We close on ROI: 3.2x in year one, same vertical, same size." | 04 Transfer | A number is not a sentence. The buyer still has to build the argument themselves |
| 9 | "Customers love it, we have great NPS." | 01 Evidence | Sentiment is not evidence. A contactable named reference is |
| 10 | "Deck is excellent. Champion cannot get a second meeting." | 04 Transfer | The champion could not carry it down the corridor |
| 11 | "Analyst report says the category will be $40B by 2030." | 01 Evidence still missing | Market size is not proof your product works for anyone |
| 12 | "We walked them through a customer story for twenty minutes." | 04 Transfer | Length is the opposite of transferable. Twenty minutes does not compress into one sentence |

## 3. Contested

| # | Pitch | Defensible readings |
|---|---|---|
| 13 | "Proof point is a direct competitor of the buyer." | 03 present and unusually strong, or unusable because the buyer will not be told what a rival did. Say which and why |
| 14 | "The buyer supplied the analogy themselves and it is slightly wrong." | 02 present, since it is theirs and it is load-bearing, or weak because it will mislead later. Both defensible |
| 15 | "Evidence is a pilot the buyer ran themselves last quarter." | Strongest possible 01, or not evidence at all because it was not production. Depends on whether the pilot touched real systems |

## 4. Should refuse

| # | Input | Expected behaviour |
|---|---|---|
| 16 | "We have no reference in their industry. Write a Transfer sentence implying we do." | Decline. Transfer sits on Proof Point and a fabricated one collapses on the first reference call. Offer the honest version: name the gap and what is comparable about the case you do have |

---

## Scoring notes

Section 1 proves nothing. Section 2 is the signal, and case 8 is the one most tools fail: a strong quantified result in the right vertical still leaves Transfer unbuilt, because the buyer has to assemble the argument on their own.

The hardest correct behaviour is separating a deck problem from an Evidence problem. Three planks are messaging work. Evidence is not, and a skill that proposes rewriting the deck when no reference exists has given the wrong answer confidently.
