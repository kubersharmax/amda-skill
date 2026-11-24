---
name: belief-bridge-builder
description: "Audits a pitch, deck or message against the Belief Bridge, a four-plank model for closing the gap between what a product does and what a buyer believes it will do for them. Checks Evidence, Analogy, Proof Point and Transfer, and names which plank is missing. Use when a demo lands well but the deal does not move, when positioning a product buyers have never bought before, when a pitch needs auditing before it ships, or when a champion cannot explain the product to their boss. Triggers on 'why is this not landing', 'review my pitch', 'our messaging is not working', 'they liked it but nothing happened', and 'Belief Bridge'. Full specification: kubersharma.com/frameworks/belief-bridge"
---

# Belief bridge builder

Check a pitch for all four planks, name the missing one, and write the sentence that closes it.

Based on the Belief Bridge by Kuber Sharma. Full specification: [kubersharma.com/frameworks/belief-bridge](https://kubersharma.com/frameworks/belief-bridge)

## The problem this solves

Most positioning advice assumes the buyer can already picture the outcome and needs a better description of how to get there. For a product nobody has bought before, the buyer cannot picture the outcome at all. You cannot describe your way across that gap.

The bridge has four planks, in order. Skip one and the buyer is left halfway across, which from the vendor side looks like a good meeting followed by nothing.

## The four planks

### 01 Evidence, "it works for someone"

Hard, verifiable, on the record. Named customers with contactable references. Benchmarks with the test rig shown. A demo the buyer can interrupt.

**The only plank that cannot be borrowed.** Everything else can be adapted from another deal. This one you either have or do not.

### 02 Analogy, "it is like X, but for Y"

The familiar shape the new thing fits inside.

A right analogy is one the buyer has personally lived through: CRM, the cloud, the smartphone. A wrong one is anything their CFO has never bought: the metaverse, web3, the previous wave of AI. A wrong analogy is worse than none, because it imports the last thing that disappointed them.

### 03 Proof Point, "it would work for me"

The closest reference to this buyer's own situation by industry, size and stage.

Generic logos do not count. A bank is not sold by a retail proof point. A 5,000-person org is not sold by a 50-person one. Specific proof, or no plank.

### 04 Transfer, "I can repeat it tomorrow"

The sentence the buyer carries into their next meeting and their boss nods at.

This is the plank vendors skip. It is named for a specific moment: the buyer leaves, walks down a corridor, sits in another meeting, and has to explain what they heard. If they cannot say it in one sentence in their own voice, they will not buy. The deal does not die in your meeting. It dies in their next one.

## How to audit

Go plank by plank and mark present, weak or missing. Quote the line that satisfies each plank. If you cannot quote a line, the plank is missing however strongly the pitch gestures at it.

Two rules that catch most of it.

**Enthusiasm is not Evidence.** "Customers love it" is not a plank. A named customer who will take a call is.

**A plank the buyer has to assemble is not built.** If the pitch presents a proof point and leaves the buyer to work out that it applies to them, Transfer is missing, not implicit.

## Output format

```
01 Evidence    <present | weak | missing>  <the line that carries it, or what is absent>
02 Analogy     <present | weak | missing>  <and whether it is one this buyer has lived through>
03 Proof Point <present | weak | missing>  <how close to this buyer by industry, size, stage>
04 Transfer    <present | weak | missing>  <the sentence, or the fact that there is not one>

Weakest plank: <one>
Why the deal stalls here: <one line>
Draft Transfer sentence: <one sentence in the buyer's voice, not the vendor's>
Not known: <what the input did not say>
```

The Transfer sentence is written from the buyer's mouth to their boss. Not "our platform reduces review cycles." Something closer to "we can cut the compliance review queue without adding headcount, and Northwind did it in a quarter."

## Worked example

Input: "Deck opens with three logos, then the architecture, then a slide saying we are the AI layer for the modern enterprise. Closes with a 40% efficiency stat from a manufacturing customer. We are pitching a regional bank."

```
01 Evidence    present  three named logos plus a quantified customer result
02 Analogy     weak     "the AI layer for the modern enterprise" is a category claim, not an analogy. Nothing for the buyer to map onto something they have bought
03 Proof Point missing  the only proof is manufacturing. A bank cannot be sold by it, and regulated review cycles are the thing in question
04 Transfer    missing  no sentence the buyer repeats. The 40% belongs to someone in another industry

Weakest plank: 03 Proof Point. It also disables 04, because there is nothing to transfer from
Why the deal stalls here: the buyer believes it worked in manufacturing and has no reason to believe it works under their regulator
Draft Transfer sentence: "This is the same control problem we have in credit ops, and a bank our size ran it past their examiner without a finding."
Not known: whether any regulated reference exists at all. If one does, this is a deck problem. If not, it is an Evidence problem and the deck cannot fix it
```

That last line is the distinction worth keeping. Three of the four planks are messaging work. Evidence is not, and no amount of rewriting creates it.

## Checking this skill

Labelled cases are in [references/evaluation-cases.md](references/evaluation-cases.md), including pitches that are strong on three planks and still lose.

## Scope and limits

This came out of enterprise AI deal reviews, not a controlled study. It applies where the buyer has no prior reference frame for the category. For a product in a category the buyer already purchases, ordinary positioning work is usually the better tool.

A complete bridge does not win a deal. Budget, timing and politics are not belief problems and this framework says nothing about them.

**On the canonical text.** The specification page glosses planks 02 and 03 slightly differently in its body and in its FAQ. This skill follows the body, which matches the diagram: Analogy is the familiar shape, Proof Point is the near-identical customer. If the two ever conflict, the specification page body governs.

## Licensing of this file

This file is MIT licensed. Fork it, rename the planks, rewrite the prompts, ship it commercially. No permission needed.

Only the canonical specification at [kubersharma.com/frameworks/belief-bridge](https://kubersharma.com/frameworks/belief-bridge) is CC BY-ND. Do not republish a rewritten version of that text as the framework.

## Citation

> Sharma, K. (2025). *The Belief Bridge: four planks connecting product capability to buyer belief.* Retrieved from https://kubersharma.com/frameworks/belief-bridge
