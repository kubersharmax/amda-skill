---
name: pilot-trap-auditor
description: "Audits an enterprise AI pilot against the Pilot Trap, a five-stage model of why pilots stall before production, and the six infrastructure gaps that cause it. Use when a pilot is being scoped, when a pilot works in a demo but has not deployed, when asked why AI initiatives never reach production, when a review meeting keeps slipping a quarter, or when deciding what to fix before a pilot starts. Triggers on 'our pilot is stuck', 'why did the POC not ship', 'production readiness', 'the pilot worked but', and 'Pilot Trap'. Full specification: kubersharma.com/frameworks/pilot-trap"
---

# Pilot trap auditor

Locate an enterprise AI pilot on a five-stage arc, then name which of six infrastructure gaps are still open and who has to close each one.

Based on The Pilot Trap by Kuber Sharma. Full specification: [kubersharma.com/frameworks/pilot-trap](https://kubersharma.com/frameworks/pilot-trap)

## The problem this solves

Enterprise AI pilots do not usually fail. They stall, and then they are abandoned by the absence of a decision to continue them. The workload goes on being handled the old way and nobody can point to the meeting where it was called off.

The reason is that a pilot is scoped to prove a capability, while production demands something else entirely. Success in a pilot means the model gave good answers. Success in production means a named person owns what the agent does on a Tuesday in Q3. Those are different projects, and the second one is rarely funded.

This skill finds where a given pilot sits on that arc and what is unclosed.

## How to use this skill

Describe the pilot in plain language. Useful detail, where known: what it does, who sponsors it, how long it has run, what the success criteria are, who owns it after launch, and whether security, procurement and legal have seen it.

You can also run it before a pilot starts, which is the better use. Auditing at Scoping changes the outcome. Auditing at Stall mostly documents it.

Partial information is fine. Say which inputs were missing rather than guessing at them.

## The five stages

Place the pilot at one stage. Use the diagnostic question, not the team's own description of where they are.

### 01 Excitement

A leader saw a demo. A group formed. Budget was approved informally.

**Diagnostic:** is there a written success criterion that someone outside the enthusiastic group has agreed to? If no, the pilot is at Excitement regardless of how much work has been done.

### 02 Scoping

A use case is chosen. It is usually chosen for how well it demos, not how well it deploys. The boundary is drawn around what the model can do rather than what the workflow requires.

**Diagnostic:** were IT security, procurement and legal in the room? If they were not, the pilot is being scoped against the wrong calendar.

**This is the only stage where an audit changes the outcome.**

### 03 Sandboxing, where the trap springs

The pilot is built somewhere with none of the integrations, none of the policies and none of the people who own production. It works, and it works beautifully.

Then production calls, and brings three friends. IT security wants to know how the agent handles secrets. Procurement wants to know what is in the EULA. Legal wants to know what happens when the agent gets something wrong. None of the three were at the demo. They are now setting deployment terms that differ from the terms the pilot was built against.

**Diagnostic:** does the pilot environment share identity, data and policy with production? If not, the demo is not evidence about deployment.

### 04 Stall

Nothing fails. The review slips a quarter, then two. The sponsor moves to the next priority. Success criteria stay unsigned.

**Diagnostic:** has the review date moved more than once? One slip is a calendar. Two is a diagnosis.

### 05 Abandonment

Nobody decides to stop. The workload returns to whoever did it before, and the pilot survives only in a slide and a CV line.

**Diagnostic:** can anyone name the person who decided to end it? If not, this is Abandonment rather than a decision.

## The six infrastructure gaps

Stages say when. Gaps say why. Check each one and mark it closed, open or unknown. Unknown is a finding, not a blank.

| Gap | What it looks like on a Tuesday | Probe |
|---|---|---|
| **Data** | The model works on clean demo data. Production data has three formats and one stopped updating in March. | What is the worst real record this has been run against? |
| **Integration** | The API exists. Getting it into the stack needs a ticket, a security review and a VP signature nobody budgeted for. | How many systems does production need, against how many the pilot uses? |
| **Accountability** | The pilot has a sponsor. Production needs an owner. Nobody has volunteered. | Name the person accountable for an agent decision after launch. |
| **Measurement** | Pilot success was "the model gave good answers." Nobody agreed what production success means. | What number changes, and who already reports it? |
| **Change management** | The team whose process is being replaced has not been told. | Who loses a task, and when were they told? |
| **Economic** | IT absorbed the pilot cost. The production cost belongs to a business unit that did not budget for it. | Whose budget line carries this next year? |

A sponsor is not an owner. A sponsor approves. An owner answers for the output. Pilots routinely have the first and almost never have the second, and the Accountability gap is the one most often marked closed when it is not.

## What to do about it

The trap springs at Sandboxing, so the intervention belongs at Scoping. Put the three friends in the room then. Their answer is rarely yes, and usually not until next quarter. That is the point. A pilot designed against the right calendar deploys. A pilot designed against the wrong calendar is theatre.

Treat the pilot as a production requirements exercise rather than a capability proof. Map the six gaps before it runs, name the owner, define the production metric, and fund the gap-closing work. Then run the pilot to test those assumptions, not to prove the model works in a clean room.

## Output format

```
Stage: <01-05> <name>
Why: <the diagnostic that placed it, in one line>

Gaps:
  Data              <closed | open | unknown>  <one line>
  Integration       <closed | open | unknown>  <one line>
  Accountability    <closed | open | unknown>  <one line>
  Measurement       <closed | open | unknown>  <one line>
  Change management <closed | open | unknown>  <one line>
  Economic          <closed | open | unknown>  <one line>

Most likely cause of stall: <one gap, named>
Next action: <one thing, with the person who has to do it>
Not known: <inputs that were missing>
```

Name one next action, not six. A list of six is the same as none.

## Worked example

Input: "Our support summarisation pilot has been running five months. The demo is great, everyone loves it. Security came back last month with questions about where transcripts are stored. The QBR moved from October to January."

```
Stage: 04 Stall
Why: review date has moved once already and security arrived after the build, not before

Gaps:
  Data              unknown  transcript retention and format in production not stated
  Integration       open     security questions about storage imply the pilot store is not the production store
  Accountability    unknown  no owner named for summaries that are wrong
  Measurement       open     "everyone loves it" is not a production criterion
  Change management unknown  support team impact not mentioned
  Economic          unknown  no budget owner named

Most likely cause of stall: Measurement. There is nothing signed to hold the January date against.
Next action: get the support operations lead to put one number and one threshold in writing before the January QBR.
Not known: data retention, owner, budget line, support team awareness.
```

Note that four of six came back unknown on a fairly detailed description. That is normal and it is itself the finding.

## Checking this skill

Labelled cases, including pilots that look healthy and are not, are in [references/evaluation-cases.md](references/evaluation-cases.md). Run the contested ones rather than the obvious ones.

## Scope and limits

The pattern comes from observation across four companies and two technology eras, not from a controlled study. It is a diagnostic aid, not a prediction. A pilot can clear all six gaps and still be cancelled for reasons that have nothing to do with readiness.

The model describes enterprise deployments with procurement and security functions. It says little about a two-person company, where none of the three friends exist.

Do not present the stage as a verdict on the team. Most pilots reach Stage 04 through ordinary incentives, not incompetence.

**Name collision.** "The Pilot Trap" is also the title of a 2026 book by Vijayan Seenisamy arguing a different thesis. This framework is unrelated to that book.

## Licensing of this file

This file is MIT licensed. Fork it, rewrite the stages, change the probes, ship it inside a commercial product. No permission needed.

The only thing under CC BY-ND is the canonical framework specification at [kubersharma.com/frameworks/pilot-trap](https://kubersharma.com/frameworks/pilot-trap). Do not publish a rewritten version of that canonical text as the framework. The boundary is the repository, not a paragraph inside it.

## Citation

> Sharma, K. (2025). *The Pilot Trap: a five-stage pattern for why enterprise AI stalls before production.* Retrieved from https://kubersharma.com/frameworks/pilot-trap
