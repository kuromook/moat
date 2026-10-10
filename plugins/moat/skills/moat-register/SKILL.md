---
name: moat-register
description: Write the pre-registration for a measurement before it runs — arms, primary value, strata, bars, and what each outcome will mean. Use when the user says to pre-register, or before starting any run whose result will be reported.
---

# moat-register

Produce a registration **file**, committed before any score exists. Chat is not
a registration; neither is a plan you remember.

Ask only for what you cannot infer, then write the file:

```
## Question
One sentence. It must be answerable "no".

## Arms
Each arm, its inputs, and what it is for. Include by default:
  - do nothing
  - do everything (and whether its score is an identity)
  - the existing tool alone, with no model
  - a no-training frequency table over one cheap descriptor

## Primary value
One number, one definition, and the strata it is read on separately.
Say what is pooled and what is never pooled.

## Instrument checks (IC1..)
At least one cell whose value is known from OUTSIDE this pipeline.
State the value now. If it does not reproduce, nothing in the run is read.

## Negative controls (NC1..)
One named concrete error each, with its expected score written now.
Name the layer the error happens in, not a direction.

## Pass criteria (C1..)
For each: the bar, and WHAT EACH OUTCOME MEANS, including the one that
says this whole line of work is wrong. If no outcome would change what
you do, stop here -- there is nothing to measure yet.

## What this run cannot settle
The readings this design does not license, written down before anyone
is tempted to take them.
```

Then: commit it, print the path, and say plainly that it is fixed. If the run
later needs a different bar, that is an amendment with its own timestamp and its
own reason, made **before** the scores are read — never a rewrite.

Two failure modes to check for before you hand it over:

- **A criterion that cannot fail.** If an arm given the answer would pass, or if
  every plausible outcome reads as support, the criterion is decoration.
- **A primary value that is an identity.** If the trivial arm's score equals a
  property of the target by arithmetic, say so in the registration, not after.
