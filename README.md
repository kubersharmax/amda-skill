# AMDA decision router

**A Claude skill that tells you which AI outputs need a human, and which ones do not.**

Point it at a workflow, a task, or a list of forty of them. It sorts each one into AI-Primary, Collaborative, or Human-Primary, gives you the governance rule for that zone, and names what breaks if you get it wrong.

Built on the [Augmented Marketing Decision Architecture](https://kubersharma.com/frameworks/amda), a framework developed in an enterprise product marketing function and observed across 16 product launches.

---

## The problem

Every AI governance policy fails in one of two directions.

**Review everything.** Adoption collapses, because using the tool is now slower than doing the work by hand. People quietly go back to the old way. The policy looks responsible right up until you check the usage numbers.

**Review nothing.** Compliance exceptions accumulate quietly until one of them does not stay quiet. Legal gets involved. Within a quarter you have the first failure instead.

Both come from applying one rule to every decision. Generating forty subject lines for a test is not the same decision as approving a regulatory disclosure. This skill sorts them.

---

## Install

### If you use Claude Code or Cowork

Clone into your skills folder:

```bash
git clone https://github.com/kubersharmax/amda-skill.git ~/.claude/skills/amda-decision-router
```

Restart Claude. That is it.

### If you would rather not use the terminal

1. Click the green **Code** button at the top of this page, then **Download ZIP**.
2. Unzip it.
3. Move the folder into `~/.claude/skills/` and rename it `amda-decision-router`.
   On a Mac, `~` means your user folder. Press `Cmd + Shift + G` in Finder and paste `~/.claude/skills` to get there. If the `skills` folder does not exist, make it.
4. Restart Claude.

### If you just want to try it once

Copy the contents of [`SKILL.md`](SKILL.md) and paste it into a conversation, followed by your question. It works fine as a one-off prompt. The install just saves you from pasting it every time.

---

## Using it

Ask in plain language. Some things that trigger it:

- "Should a human review this before it goes out?"
- "Here are 30 tasks my marketing team does. Which ones can an agent own outright?"
- "Our AI adoption is terrible and everyone says the review process is why. Diagnose it."
- "Can the agent send this itself, or does someone need to approve?"
- "Draft an AI governance policy for a 20-person product marketing team."

### What comes back

For one decision:

```
Decision: Agent drafts the weekly customer newsletter and schedules it
Reversibility: low, once it sends it is in 12,000 inboxes
Exposure: high, external and customer-facing
Frequency: weekly, moderate

-> Zone 2: Collaborative
Governance: AI drafts. Human approves before send. The agent does not
hold the send permission.
If you got this wrong: govern it as Zone 1 and you will find out about
your first bad send from a customer. Govern it as Zone 3 and the
newsletter starts shipping late, then stops shipping.
```

For a list, you get a table.

---

## The three zones

| Zone | What belongs here | Governance |
|---|---|---|
| **1. AI-Primary** | Reversible, high-volume, internal only. Copy drafts, research summaries, categorization, test variants. | AI acts. Keep a log. Audit a sample, not every output. |
| **2. Collaborative** | Reaches an external audience. Reputational or compliance cost if wrong. | AI drafts. A human approves before it goes out. AI does not send. |
| **3. Human-Primary** | Irreversible, novel, or legally exposed. Someone's career is attached. | AI researches and drafts options. A named human decides. |

Sorted by stakes, not by seniority. Keep Zone 3 small. A large Zone 3 is the review-everything failure wearing a different hat.

---

## The one insight worth stealing

The failure modes are asymmetric.

Over-governing kills the programme slowly, and looks responsible the whole time it is happening. Under-governing kills it fast and visibly.

Most organizations are far more afraid of the second and far more damaged by the first.

---

## Scope and limits

The field evidence behind AMDA comes from a single observational deployment across 16 enterprise product launches in one product marketing function at Tableau, a Salesforce company, prior to 2025. It is an observational deployment study, not a controlled experiment. Results reflect one context and yours may differ.

Full methods note: [kubersharma.com/frameworks/amda](https://kubersharma.com/frameworks/amda)

A manuscript developing AMDA into a formal taxonomy is under review at the *Journal of the Academy of Marketing Science*, submitted July 2026.

---

## More

- [The full AMDA specification](https://kubersharma.com/frameworks/amda) and a [printable reference card](https://kubersharma.com/frameworks/amda-reference)
- [The other three frameworks](https://kubersharma.com/frameworks): the Pilot Trap, the Trust Architecture, the Belief Bridge
- [agentic-gtm-os](https://github.com/kubersharmax/agentic-gtm-os), where all four live in full
- [Essays on enterprise AI go-to-market](https://kubersharma.com/writing)

---

## Contributing

If you use this and the zones come out wrong for your context, open an issue and tell me what it missed. Edge cases are the useful feedback. Pull requests welcome on the skill instructions.

---

## Citation

> Sharma, K. (2026). *The Augmented Marketing Decision Architecture (AMDA): a three-zone taxonomy for human-AI decision authority in enterprise marketing.* Retrieved from https://kubersharma.com/frameworks/amda

By [Kuber Sharma](https://kubersharma.com), Senior Director of Product Marketing at UiPath.

Framework text: CC BY-ND 4.0. See [LICENSE](LICENSE).
