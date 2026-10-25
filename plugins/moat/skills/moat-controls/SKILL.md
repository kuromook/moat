---
name: moat-controls
description: Propose negative controls for a measurement — one named concrete error each, with its expected score. Use when designing controls, or when a result looks too good and you need to know which bug would produce exactly it.
---

# moat-controls

A negative control is not a direction, a vibe, or a shuffle. It is **one
concrete mistake that could actually have happened in this code**, implemented
on purpose, with its expected score written down before it runs.

For the measurement at hand, enumerate controls by walking the pipeline and
asking at each layer: *what is the plausible bug here, and what would it score?*

Classes worth covering, with the question each one answers:

| Control | What a pass tells you |
|---|---|
| Polarity / sign flipped | The convention at the input boundary is right |
| Off-by-one pairing: item *i*'s prediction against item *i+1*'s target | The score is about *this* item, not the population |
| A transform that destroys location (transpose, flip, large shift) | The overlap is placement, not amount |
| Label or identity shuffled within the same marginals | The signal is the pairing, not the base rates |
| The answer's total handed over, placement left to the method | How much of the score is quantity |
| The known broken predecessor, run as an arm | The new thing is above the old bug |

Then check each proposal against the three ways a control is born useless:

1. **It computes an impossible hybrid.** "Swap x and y" implemented at one layer
   while a downstream layer keeps the correct value is a bug that cannot occur.
   Name the layer: the axis order of a coordinate array and the transpose of a
   final mask are different errors with different signatures.
2. **It cannot fail.** If the control's object is related to the real one by a
   relabelling, symmetric statistics are identical by construction. Its pass is
   worth nothing — only an anchor outside the pipeline decides that class.
3. **It is weaker than the thing it guards.** An off-by-one control passes an arm
   that has no location information at all, because re-pairing destroys only the
   between-item differences in amount. Pair it with a location-destroying
   transform, and treat "the transform cost nothing" as the finding it is.
4. **It is scored on a different population.** A control that silently skips
   the cases it cannot construct -- no room to place the object, no valid pairing
   -- is measured on the subset where construction succeeded, and that subset is
   normally biased along the quantity of interest: the largest objects are
   exactly the ones that cannot be moved. Drop those cases from the arm as well,
   print how many, and say what they had in common.

Report every control's score **above** the primary, each with the error it
implements and its registered bar. Say which arms are therefore not read.
