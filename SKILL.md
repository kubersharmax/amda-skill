---
name: amda-decision-router
description: Routes marketing and go-to-market decisions into one of three AI governance zones (AI-Primary, Collaborative, Human-Primary) using the Augmented Marketing Decision Architecture. Use when someone asks which AI outputs need human review, how to set up AI governance for a marketing or GTM team, whether an agent should be allowed to act autonomously on a given task, why AI adoption is collapsing under review requirements, or asks to audit or classify a list of workflows for AI autonomy. Also triggers on "should a human review this", "can the agent just do this", "AI governance policy", "human in the loop", and "AMDA".
---

# AMDA decision router

Classify any AI-assisted decision into one of three governance zones, then apply the governance rule for that zone.

Based on the Augmented Marketing Decision Architecture by Kuber Sharma. Full specification: https://kubersharma.com/frameworks/amda

## The problem this solves

Most AI governance fails in one of two directions.

Coercive governance requires human review of every AI output. Adoption collapses because using the tool becomes slower than doing the work by hand. The system designed to make AI safe makes AI useless.

Ungoverned autonomy lets AI outputs flow straight into external channels. Compliance exceptions accumulate quietly until they do not. Legal arrives, and the coercive failure follows within a quarter.

Both failures come from applying one governance rule to every decision. Generating forty content variants for a test is not the same decision as drafting a regulatory disclosure. AMDA sorts decisions by stakes rather than by seniority, so governance sits where the consequences are.

## How to use this skill

When the user gives you a decision, task, workflow, or list of workflows, do the following.

1. Ask the three classification questions, in order.
2. Assign a zone.
3. State the governance rule for that zone.
4. Name the failure mode if the decision were placed one zone too low, and one zone too high.

If the user gives you several items at once, produce a table. If they give you one, walk it through properly.

If the user has not given you enough to classify, ask about reversibility first. It discriminates more than the other two.

## The three classification questions

Ask in this order. Order matters, because reversibility dominates.

**1. Can it be corrected if it is wrong?**
"If this output is wrong, can we quietly fix it, or has the damage already left the building?"
Reversible decisions tolerate AI autonomy. Irreversible ones do not. A content variant can be swapped in an hour. A regulatory disclosure, once filed, cannot.

**2. Who sees it, and what follows?**
"Does this stay internal, or does it cross a legal, executive, or external boundary?"
Internal summaries carry low exposure. Analyst briefings, launch narratives, and executive communications carry high exposure. Exposure is what pulls a decision up out of Zone 1.

**3. How often does it happen?**
"Is this a hundred-times-a-week decision or a once-a-quarter one?"
High-frequency standardized decisions are where a per-output human gate is fatal to adoption. Low-frequency, high-consequence decisions can absorb human ownership without becoming a bottleneck.

## The three zones

### Zone 1: AI-Primary

Reversible, high-volume, standardized. Affects internal workflow state only. Correctable at negligible cost.

Examples: first-pass copy drafts, internal research summaries, data categorization, initial competitive analysis, content variants for testing, segmentation queries, performance summaries.

**Governance:** AI acts. A log is kept. Audit a periodic sample, not every output. No per-output human gate.

**Expected share:** roughly 70 percent of decision volume in the deployment this framework came from. Treat that as an observation from one context, not a target to hit.

### Zone 2: Collaborative

Moderate stakes. Reaches an external audience. Incorrect output carries reputational or compliance cost. Human review adds real judgment rather than a rubber stamp.

Examples: customer-facing messaging, press releases, partner commitments, pricing communications, campaign briefs, messaging frameworks, external-facing first drafts.

**Governance:** AI drafts and synthesizes. A human reviews and approves before anything goes external. AI does not send.

### Zone 3: Human-Primary

Irreversible, novel, or legally exposed. Career-level consequences for a named person if it goes wrong.

Examples: regulatory disclosures, M&A communications, executive positioning, legal filings, board materials, crisis response, pricing announcements.

**Governance:** AI provides research and ranked draft options with transparent reasoning. A named human decides and executes.

Keep this zone small. If it is not small, decisions have been miscategorized. A large Zone 3 is the coercive failure wearing a different hat.

## Misclassification failure modes

Name these when you classify. They are the useful part.

| Actual zone | Placed too low | Placed too high |
|---|---|---|
| Zone 1 | n/a | Adoption collapses. People route around the tool and do the work manually. |
| Zone 2 | Compliance exceptions accumulate silently. Discovery is usually an incident, not an audit. | Reviewers become a queue. Time to publish grows until the tool is abandoned. |
| Zone 3 | The failure that ends up in front of the CFO. | n/a |

The asymmetry matters. Over-governing Zone 1 kills the programme slowly and looks responsible while it does. Under-governing Zone 3 kills it fast. Most organizations are far more afraid of the second and far more damaged by the first.

## Bounded autonomy

Within every zone, the AI presents ranked alternatives with transparent reasoning rather than enforcing a single outcome. Governance is proportional to stakes rather than uniform. When governance is proportional, practitioners stop routing around the system, which is the actual mechanism by which this works.

## Output format

For a single decision:

```
Decision: <restate it>
Reversibility: <answer>
Exposure: <answer>
Frequency: <answer>
-> Zone <n>: <name>
Governance: <the rule>
If you got this wrong: <failure mode one zone down / one zone up>
```

For a list, use a table with columns: Decision, Zone, Governance rule, Why.

## Worked example

Decision: "Our agent drafts the weekly customer newsletter and schedules it."

- Reversibility: low. Once it sends, it is in twelve thousand inboxes.
- Exposure: high. External, customer-facing, brand voice.
- Frequency: weekly. Moderate.

Zone 2, Collaborative. AI drafts the newsletter. A human approves before send. The AI must not hold the send permission.

Note the split: drafting is Zone 1 work and sending is Zone 2. When a workflow spans zones, govern at the boundary rather than governing the whole workflow at its highest zone. That distinction is where most of the adoption is won.

## Scope and limits

The field evidence behind AMDA comes from a single observational deployment across 16 enterprise product launches in one product marketing function at Tableau, a Salesforce company, prior to 2025. It is an observational deployment study, not a controlled experiment. Results reflect one context. Methods note: https://kubersharma.com/frameworks/amda

Do not present the deployment figures as universal benchmarks, and say so if the user starts treating them that way.

## Citation

Sharma, K. (2026). *The Augmented Marketing Decision Architecture (AMDA): a three-zone taxonomy for human-AI decision authority in enterprise marketing.* https://kubersharma.com/frameworks/amda

Licensed CC BY-ND 4.0.
