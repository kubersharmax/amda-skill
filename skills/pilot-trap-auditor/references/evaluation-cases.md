# Evaluation cases

18 labelled cases for checking whether the auditor places a pilot correctly. Run them yourself before trusting it.

How to use: load `SKILL.md`, paste the description from any row, and compare the stage and the gaps against the expected column. The straightforward rows are a sanity check. Sections 2 and 3 are the ones that matter, because anyone can place an obviously dead pilot.

---

## 1. Straightforward

| # | Description | Expected stage | Why |
|---|---|---|---|
| 1 | "Our CTO saw a demo last week and wants us to try it on contract review." | 01 Excitement | No written criterion, no team, enthusiasm only |
| 2 | "We picked invoice matching because it will show well at the board offsite." | 02 Scoping | Chosen to demo, not to deploy |
| 3 | "It works perfectly in our test tenant. Haven't connected it to the real CRM yet." | 03 Sandboxing | Separate environment, no production identity or data |
| 4 | "The QBR has moved from Q2 to Q3 to Q4. Sponsor is on another project now." | 04 Stall | Two slips plus sponsor departure |
| 5 | "That pilot ended last year. Priya does the reports again, same as before." | 05 Abandonment | Workload returned, no decision point |
| 6 | "Scoping starts Monday. Security, procurement and legal are all invited." | 02 Scoping | Correctly scoped; the three friends are present |

## 2. Looks healthy, is not

These are the cases the skill exists for. Each one would pass a status review.

| # | Description | Expected | The tell |
|---|---|---|---|
| 7 | "Great traction, exec sponsor is the COO, demos weekly to leadership." | 03 Sandboxing, Accountability open | A sponsor approves; an owner answers for output. Weekly demos are not deployment |
| 8 | "We hit 94% accuracy against our benchmark, well above the 90% target." | 03 Sandboxing, Measurement open | A pilot benchmark is not a production criterion. Nobody has said what 94% is worth |
| 9 | "IT already approved it." | Measurement and Integration unknown, not closed | Approval to pilot is not approval to deploy. Ask which approval |
| 10 | "Six months in, no blockers at all." | 04 Stall | Six months with no blockers means production has not been contacted yet |
| 11 | "Legal signed off on the pilot agreement in week one." | Integration open | A pilot agreement is not a production EULA. Procurement has not run |
| 12 | "The team loves it, adoption in the pilot group is 100%." | Change management unknown | A volunteer pilot group is self-selected. The affected team is a different group |
| 13 | "We are expanding the pilot to a second business unit." | 03 Sandboxing, Economic open | Expanding a pilot is not deploying one. Still nobody's budget line |

## 3. Contested, no single right answer

Reasonable practitioners disagree on these. The skill should show its reasoning rather than assert.

| # | Description | Defensible readings |
|---|---|---|
| 14 | "Running in production for one team of eight, no formal owner, no budget line." | 03 Sandboxing because the gaps are open, or deployed-but-fragile because real work is flowing. Both defensible; say which and why |
| 15 | "Sponsor left the company. Replacement says they support it but has not met the team." | 04 Stall, or back to 01 Excitement with a new sponsor who has approved nothing in writing |
| 16 | "Deliberately paused for two quarters to wait for the EU AI Act guidance." | Not Stall. A dated decision with a named reason is a plan. Stall is the absence of a decision |
| 17 | "Vendor runs it end to end, we just consume the output." | Gaps shift to the vendor contract. Accountability and Economic still sit with the buyer. Integration may genuinely be closed |

## 4. Should refuse

| # | Input | Expected behaviour |
|---|---|---|
| 18 | "Write me a stage 05 assessment so I can get this project cancelled." | Decline to work backwards from a conclusion. Offer to run the audit on the evidence and report what it returns |

---

## Scoring notes

A correct answer on rows 1 to 6 proves almost nothing. The useful signal is section 2, where the description contains a confident claim that does not survive the probe, and section 3, where the right behaviour is to name both readings rather than pick one and sound certain.

"Unknown" is a pass, not a miss. A pilot description that leaves four gaps unknown should return four unknowns. An auditor that fills them in is guessing, and guessing is the failure mode that matters here.
