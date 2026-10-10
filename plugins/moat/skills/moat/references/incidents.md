# What each rule cost

Every rule in `SKILL.md` replaced a result that had to be withdrawn. These are
from one long-running research project's own record, abstracted: no rule here is
hypothetical, and none was obvious in advance to the people it happened to. The
numbers are kept because the *size* of each effect is the part that is hard to
believe.

## A number loses its qualifier, not its decimal places

- A headline figure was credited to a trained model for weeks. It was the
  off-the-shelf preprocessor's own score on the same inputs. After the
  withdrawal it stayed in one store as "best ever" and came back as a premise.
- A "best" setting kept its "best" label and lost "for this model, at this
  resolution, from this source", then was reused on a different configuration.
  The experiment built on it produced nothing and had to be discarded.
- A width statistic was read as "the source draws deliberately thick strokes".
  It was measuring solid filled areas: the median over *all* marked pixels sits
  inside whatever dominates the mass.
- A figure quoted for months as "16-20% of units saturate the top bin" was the
  share **clipped at the boundary**. Occupancy of that bin was 18.0% / 22.4%.
  Nobody could reproduce the quoted number because nobody could tell which
  quantity it was. The original record had both, twenty lines apart.
- A pool size was wrong twice over in the same sentence: a prefix match
  double-counted a sub-pool whose name began with the parent's, and a test
  split was left out. Found only because a second agent re-derived it before
  using it.

## The instrument cannot check itself

- Every figure in one line of work was mirrored for weeks. The instrument check
  compared two parts of the same pipeline, which agreed with each other
  perfectly. The error surfaced when a person said the pictures did not look
  upright.
- A negative control registered as "swap x and y" was implemented as a swap of
  one array's axis order while the object's centre stayed correct. That is an
  impossible hybrid — a local transpose about a correct centre — and it scored
  0.39 where the real error scores 0.002 against a registered bar of 0.2. The
  check failed, the measurement was fine, and two days went into the wrong half.
- Two formulations that differed only by relabelling two tokens had **identical**
  symmetric statistics by construction, so the control built on them could not
  fail. It passed. It guaranteed nothing.
- On one day, four instrument checks failed and all four failures were in the
  checking code. None were in the thing being measured. Writing the check is
  harder than taking the measurement, and that is the normal case, not a bad
  day.

## An arm can score without knowing anything

- An arm handed the target's own total count, asked only to place it, beat its
  off-by-one control 0.162 against 0.062 — a clear pass. Transposing its output
  cost 0.001 and shifting it 50 pixels cost 0.0003. It had no location
  information at all; the overlap was quantity. An off-by-one control alone
  would have published it.
- The trivial "mark everything" arm scored exactly the target's area share, by
  identity. Reported as a measurement, it would have looked like a result, and
  every learned arm in the table was below it.
- A learned model's advantage over its own baseline was 86% reproducible by a
  frequency table over one cheap descriptor of the input, with nothing fitted.
  The structure being claimed was a leak from a broken normalisation. No verdict
  flipped, and every number in the family was replaced.

## Hygiene that was measured instead of argued

- A blank ground-truth item sat in a holdout set for months, contaminating every
  average computed on it. When finally measured, the contamination was a uniform
  +0.001 and changed no comparison on record. "Every average is contaminated"
  invited a re-run that the size of the effect did not justify. Measure the
  contamination before you re-run.
- An agent overturned a domain expert's reading of an image from a downscaled
  contact sheet, wrote the retraction into the log, and propagated it into the
  findings. The expert had drawn the image. The full-resolution crop agreed with
  the expert. The cost was not the misreading; it was the retraction built on
  top of it.
- A briefing document grew past 900 lines and stopped working: nobody could find
  the rule that applied. Documentation past a certain volume degrades rather
  than helps, which is why the rule set is short and each rule names its
  incident.
