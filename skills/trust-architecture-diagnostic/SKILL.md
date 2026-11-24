---
name: trust-architecture-diagnostic
description: "Diagnoses which of three sequential trust layers is blocking an enterprise AI deal: Technical (does it work at our scale), Operational (can my team run it when it breaks at 3am), Strategic (will my career survive it if this goes wrong). Use when a deal has stalled without a stated objection, when a technically successful POC is not converting, when deciding what evidence to put in front of a buyer next, or when a champion has gone quiet. Triggers on 'the deal stalled', 'they loved the demo but', 'why are we not closing', 'what does this buyer need to see', and 'Trust Architecture'. Full specification: kubersharma.com/frameworks/trust-architecture"
---

# Trust architecture diagnostic

Find which of three trust layers a buyer is stuck on, then name the evidence that moves them up one layer and no further.

Based on the Trust Architecture by Kuber Sharma. Full specification: [kubersharma.com/frameworks/trust-architecture](https://kubersharma.com/frameworks/trust-architecture)

## The problem this solves

Buyers climb three layers in order. Vendors pitch them in reverse. That mismatch is where enterprise AI deals die, and it looks from the inside like an unexplained stall.

The buyer has usually accepted the capability already. They are asking a different question, and a vendor answering the wrong one sounds evasive rather than reassuring.

## The three layers

They are sequential, not parallel. A buyer without Technical Trust will not engage with Operational Trust. A buyer with Technical but not Operational Trust will not hear the Strategic pitch at all.

### 01 Technical Trust, does it work

*"Will this actually do what you say, reliably, at our scale?"*

The easiest layer. Demos, benchmarks and reference architectures answer it. Necessary, and the layer most often mistaken for sufficient. A vendor who never leaves this layer is running a pilot that never ships.

### 02 Operational Trust, can my team run it

*"Can the operations team I already have, with the tools we already use, support this when it breaks at 3am?"*

Answered by runbooks, escalation paths, SLA commitments and live operations examples. The real question is whether the existing org chart absorbs the product without hiring three roles and rebuilding two pipelines. Most enterprise AI fails here, after the technical demo passed.

### 03 Strategic Trust, will my career survive it

*"If this goes wrong, am I the one explaining it to the CFO?"*

Answered by executive sponsorship evidence, regulatory alignment, rollback capability, and reference customers carrying comparable risk. Nobody puts this layer on a slide. The buyer is a person with a career and a mortgage, and a vendor who ignores this is negotiating with someone who has already privately said no.

## How to diagnose

Listen for the question actually being asked, not the one on the agenda. The layer is usually identifiable from a single sentence.

| What you hear | Layer they are on |
|---|---|
| "Can it handle our volume?" "What is the accuracy on our data?" | 01 Technical |
| "Who supports this?" "What happens at 2am on a Sunday?" "Does this need new headcount?" | 02 Operational |
| "What do I tell the board?" "Has anyone in our industry done this?" "Can we turn it off?" | 03 Strategic |
| Silence after a successful demo | 02 or 03. Silence is not neutral, it is an unasked question |

Two traps worth naming.

**A question from a lower layer after you have moved up means you moved too early.** Going back is correct, not a setback.

**Enthusiasm is not trust.** A champion who loves the product and cannot get a meeting is blocked at Strategic, usually on someone else's behalf.

## Why agentic AI raises the stakes

Traditional software produces output a human accepts or rejects. An agent acts: it touches live systems and takes consequential actions without approval at each step. A buyer who trusts a tool to suggest does not automatically trust an agent to execute, so every layer has to be satisfied again at a higher threshold before autonomy is extended.

## Output format

```
Layer they are on: <01 | 02 | 03> <name>
Evidence for that: <the quote or behaviour that places them>

What you are currently pitching: <layer, if it can be told from the input>
Mismatch: <yes and in which direction | no | cannot tell>

Next evidence to put in front of them: <one artefact, named>
Who has to provide it: <role>
Do not yet: <the thing that would skip a layer>
Not known: <missing inputs>
```

Name one artefact, not a list. A vendor who sends five things has told the buyer they do not know which layer the buyer is on.

## Worked example

Input: "POC went great, accuracy beat their bar. Champion is keen. Legal asked for our incident history last week and it has gone quiet since."

```
Layer they are on: 03 Strategic
Evidence for that: legal asking for incident history is a question about blame, not capability. The silence began there

What you are currently pitching: 01 Technical, the accuracy result
Mismatch: yes. Two layers below where the buyer is

Next evidence to put in front of them: a reference customer in the same regulated category who can describe an incident and what happened next
Who has to provide it: your exec sponsor, to theirs. Not the AE
Do not yet: send more accuracy data. It answers a question nobody is asking now
Not known: whether Operational Trust was ever established, or skipped because the POC went well
```

That last line matters. A deal can reach Strategic with Operational never actually closed, and it will fall back.

## Checking this skill

Labelled cases, including deals that look like one layer and are another, are in [references/evaluation-cases.md](references/evaluation-cases.md).

## Scope and limits

This is a diagnostic drawn from observation across enterprise deals at four companies, not a controlled study. It describes enterprise buying with security, procurement and legal functions, and says little about self-serve or small-business purchase.

It will not tell you a deal is winnable. Plenty of deals stall for budget, timing or politics that no amount of trust evidence addresses. Diagnosing a layer is not the same as having a path.

Do not use the layer as a label for the buyer. It describes where a conversation is, not how sophisticated the person is.

## Licensing of this file

This file is MIT licensed. Fork it, rename the layers, rewrite the cues, ship it commercially. No permission needed.

Only the canonical specification at [kubersharma.com/frameworks/trust-architecture](https://kubersharma.com/frameworks/trust-architecture) is CC BY-ND. Do not republish a rewritten version of that text as the framework.

## Citation

> Sharma, K. (2025). *The Trust Architecture: three sequential layers of enterprise buyer trust.* Retrieved from https://kubersharma.com/frameworks/trust-architecture
