---
name: moat
description: Use when work produces, reads or reports a measurement — designing an experiment or benchmark, scoring a model or a pipeline, choosing a metric, building an evaluation set, writing up a result, or deciding what a number means. Not for ordinary feature or UI work, where no claim rides on the code.
---

# Moat

Fill the outer moat before you report the number.

A measurement is worth having only if it could have come out the other way and
you would have had to say so. Most of the cost of research is not computing the
number, it is the work that makes the number **refusable**: the control that
would have exposed it, the cell whose value you already knew, the bar you wrote
down before you looked. That work is never requested, by anyone, ever. Build it
anyway. It is not overhead on the result — above a certain point it *is* the
result, and a number without it is a rumour with a decimal point.

This is deliberately expensive, and it is the opposite of a minimality skill.
It applies to measurement code and to reported numbers. It does not apply to
feature work, UI, glue or one-off scripts that no claim rides on. If you are
unsure which you are doing, ask: *if this came out the other way, would anything
I say change?* If nothing would, this skill is not for that task.

## The order

Work down it. Do not start the run until the step above is done.

1. **Register before you look.** In a file, committed: the arms, the primary
   value, the strata it is read on, the pass/fail bars, and **what each outcome
   will mean**. Writing down what a failure would mean is the step that catches
   a question that cannot fail.
2. **Anchor one cell outside the pipeline.** Include one quantity whose value is
   already known — from a previous run, a published figure, a hand-computed
   case, another implementation. **If it does not reproduce, nothing else in the
   run is read.** An agreement between two parts of one pipeline is not an
   anchor; it is the pipeline agreeing with itself.
3. **One negative control per named error.** Each control implements one
   concrete mistake that could actually have happened, with its expected score
   written down first. "Swap x and y" is not a named error — name the layer it
   happens in, because the transpose of a coordinate array and the transpose of
   a final mask are different bugs with different signatures. A control nobody
   could fail is not a control.
4. **Checks and controls print before the primary.** In the same report, above
   it. An arm that fails its control **is not read**, and its number does not
   appear in the headline, the abstract or the summary table without the words
   that say it failed.
5. **The trivial solutions are arms, not rhetoric.** Do nothing. Do everything.
   The existing tool alone, with no model. Each gets a row. **If a trivial arm's
   score is an identity, say which identity** — "paint every pixel" scoring
   exactly the target's area share is one number, not two, and every other arm
   is then being compared against arithmetic.
6. **A number travels with its quantity, its configuration and its bar.** Not
   `0.26 (best)` but `0.26 (model B / 1024px / held-out split, bar 0.24)`.
   **A verdict word travels with its threshold**: "localised", "significant",
   "saturated" and "large" are unreadable without the number they were judged
   against. Most repeated-number damage is a value re-read as the quantity the
   reader expected, which no amount of care at the reading end can prevent.
7. **Put a no-training table beside every learned number.** One cheap
   descriptor, a frequency table, nothing fitted. If it reproduces most of the
   learned gain, what you measured was the descriptor.
8. **Keep populations apart.** Do not average across pools that are different
   tasks, and do not let near-empty units into a mean — they reward an arm for
   the cases where there was nothing to find. Report each separately, always,
   even when the means agree.
9. **A retraction is a pass, not an entry.** When a number is withdrawn, correct
   every place that repeated it, in the same sitting, and say what replaced it.
   A withdrawn number that stays in one store comes back as a premise.
10. **On what the data depicts, the domain expert decides.** Your reading of an
    image, a recording or a transcript is a hypothesis for them to confirm,
    never grounds to overturn their judgement. When a judgement is in doubt,
    pull the raw item at full resolution instead of arguing from the summary.

## Never

- **Never relax a bar after seeing the result.** If the bar was wrong, say it
  was wrong, report the result against both, and register the new one before the
  next run. Pre-registration is "fix the criteria before seeing the results",
  which is also "do not move the results to suit new criteria".
- **Never report a mean without the n and the spread of the thing being
  averaged**, and never a micro-average without saying what it pools over.
- **Never let a number cross a document boundary without its unit.** Shares of
  ink, of area, of rows and of attempts are four quantities with one
  vocabulary.
- **Never explain a surprising number before suspecting the instrument.** The
  first question for a result better than expected is which bug would produce
  exactly this.

## When a control fires

Controls are the cheapest findings in the project, so read them as results, not
as chores:

- **An arm beats the shifted control but survives a transform that destroys
  location.** Then the overlap is *amount*, not placement. A control that
  removes location must cost a localised arm something; if the score survives
  it, an off-by-one control alone would have waved the arm through.
- **A control passes by construction.** Two formulations that differ only by a
  relabelling have identical symmetric statistics, so a control built on one
  cannot fail. Its pass guarantees nothing. Only an external anchor can decide
  that class of error.
- **A summary statistic over a mixed population reads the dominant
  subpopulation.** A median over "all of it" is a measurement of whichever part
  dominates the mass. Recompute it over the part you meant, especially before
  comparing two window sizes, two resolutions, or two sources.

## Tools

`references/incidents.md` holds the incidents these rules were paid for, each
abstracted from one research project's record. Read it when a rule looks like
pedantry; every line of this file replaced a result that had to be withdrawn.
