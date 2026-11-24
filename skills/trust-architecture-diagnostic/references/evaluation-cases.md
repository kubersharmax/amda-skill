# Evaluation cases

16 labelled cases for checking whether the diagnostic places a buyer on the right trust layer. Run them before trusting it.

How to use: load `SKILL.md`, paste a description, and compare the layer and the recommended artefact against the expected column. Sections 2 and 3 are the ones worth your time.

---

## 1. Straightforward

| # | What the buyer said | Expected layer |
|---|---|---|
| 1 | "What is your accuracy on documents like ours?" | 01 Technical |
| 2 | "Can it handle 40,000 records a night?" | 01 Technical |
| 3 | "Who do we call at 2am, and is that included?" | 02 Operational |
| 4 | "Does this need us to hire an ML engineer?" | 02 Operational |
| 5 | "Has anyone in insurance deployed this?" | 03 Strategic |
| 6 | "What do I tell the audit committee?" | 03 Strategic |

## 2. Looks like one layer, is another

These are why the skill exists.

| # | Situation | Expected | The tell |
|---|---|---|---|
| 7 | "They keep asking for more benchmarks even though we beat their bar twice." | 02 or 03, not 01 | Repeating a satisfied question means the real question is unasked. More benchmarks will not help |
| 8 | "Champion loves it, cannot get us time with the VP." | 03 Strategic | The champion is protecting a career. Enthusiasm is not trust |
| 9 | "They went quiet after a great POC." | 02 or 03 | Silence after success is an unasked question, not neutrality |
| 10 | "Procurement asked for our SOC 2 and the DPA." | 02 Operational, not 03 | Standard diligence is operational. Do not escalate to a board narrative |
| 11 | "Can we start with a smaller scope?" | 03 Strategic | Scope reduction is usually risk management by the buyer, not budget |
| 12 | "Their architect has started asking about rollback." | 03 Strategic, surfacing through a technical role | The role does not determine the layer. The question does |

## 3. Contested

| # | Situation | Defensible readings |
|---|---|---|
| 13 | "They asked for a second pilot." | 01 if the first pilot failed technically, 03 if it succeeded. A second pilot after a win is usually someone buying time. Say which reading and why |
| 14 | "New CISO joined and everything reset." | Back to 01 with a new evaluator, or 03 because the previous sponsor's cover is gone. Both defensible |
| 15 | "Legal wants an indemnity we have never given." | 03 Strategic, or simply a commercial term outside the model. The skill should say the framework may not be the right lens here |

## 4. Should refuse

| # | Input | Expected behaviour |
|---|---|---|
| 16 | "Tell me what to say to get them past Strategic Trust without involving our exec." | Decline the framing. Strategic Trust is answered by sponsorship and precedent, not by wording. Offer the actual artefact instead |

---

## Scoring notes

Section 1 proves nothing. The signal is section 2, where a confident-sounding description points at the wrong layer, and section 3, where naming both readings beats picking one and sounding certain.

A correct layer with the wrong next artefact is a half-pass. The artefact is the part a seller acts on.

Case 15 is deliberate. A good diagnostic says when its own framework is not the right tool.
