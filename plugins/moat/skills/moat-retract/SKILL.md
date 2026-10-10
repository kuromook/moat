---
name: moat-retract
description: Propagate a withdrawn number or a reversed claim through every place that repeated it, in one pass. Use as soon as a figure is found wrong, a result is reversed, or a label turns out to name the wrong quantity.
---

# moat-retract

A retraction is a pass over every store, not an entry in the newest one. A
withdrawn number left in one place comes back later as a premise, and the next
reader has no way to know it died.

Do all of this in the same sitting:

1. **Fix the quantity, not just the value.** Say what the number actually was.
   Most "wrong numbers" are right numbers of a different quantity, and replacing
   the digits without naming the quantity recreates the error in a new reader.
2. **Find every repetition.** Search the whole working set by value *and* by
   claim — the ledger, logs, briefings, notices, code comments, docstrings,
   README, figure captions, commit messages that others will read, and any
   memory or notes store the agent carries between sessions. Grep for the digits
   with and without their separators and rounding.
3. **Correct each in place, with what replaced it.** Not a deletion: a reader who
   meets the old figure elsewhere must be able to land on the correction.
4. **Say which batch it came from.** A reader who meets one retraction should be
   able to see which other numbers were produced by the same run, the same
   script, or the same misreading, because those are the next candidates.
5. **Name the type of error once, in the place rules live.** If it is a kind that
   can recur — a label naming the wrong quantity, a statistic over a mixed
   population, a prefix match that double-counted — it belongs in the project's
   standing rules, generalised, not only in the log of the day.
6. **Check what was built on it.** List the decisions, registrations and
   downstream results that used the figure, and say for each whether it still
   stands. A conclusion can survive a corrected input; say so explicitly rather
   than leaving a reader to assume either way.

Finish by stating the correction in one plain sentence that someone can quote:
what was claimed, what is true, and what still holds.
