**English** | [日本語](README.ja.md)

# Moat

**Fill the outer moat before you report the number.**

A skill set for AI coding agents doing *research* rather than shipping: work
whose output is a claim about a measurement. It keeps the agent from handing you
a number you cannot refuse.

Most of the cost of research is not computing the result. It is the work that
makes the result refusable — the control that would have exposed it, the cell
whose value you already knew, the bar written down before anyone looked. Nobody
ever asks for that work. An agent optimising for the shortest path to an answer
will skip all of it, and the answer will look exactly the same.

This is deliberately expensive. If you want an agent that builds the smallest
thing that works, use a minimality skill — several good ones exist, and this is
not a competitor to them. Use this one where a wrong number costs more than a
wasted afternoon.

## What it does

`moat` is always-on guidance for measurement work. Ten rules, each of which
replaced a result that had to be withdrawn, in order of when they apply:

1. Register the bars — and what each outcome will mean — before you look.
2. Anchor one cell outside the pipeline; if it does not reproduce, read nothing.
3. One negative control per **named** error, with its expected score written first.
4. Checks and controls print **above** the primary value. Failed arms are not read.
5. The trivial solutions are arms: do nothing, do everything, the existing tool alone.
6. A number travels with its quantity, its configuration and its bar; a verdict word travels with its threshold.
7. Put a no-training frequency table beside every learned number.
8. Keep populations apart. No averaging across different tasks, no near-empty units in a mean.
9. A retraction is a pass over every store, not an entry in the newest one.
10. On what the data depicts, the domain expert decides.

Plus four commands:

| Command | What it does |
|---|---|
| `/moat-register` | Writes the pre-registration file — arms, primary value, strata, instrument checks, controls, pass criteria, and what this run cannot settle. Refuses criteria that cannot fail. |
| `/moat-controls` | Proposes negative controls, one named concrete error each, and checks each against the three ways a control is born useless. |
| `/moat-audit` | Reads a finished result, report or draft and reports what cannot be trusted: bare numbers, verdict words without thresholds, unread arms in the headline, pooled populations, bars that moved, missing trivial arms, unanchored instruments. |
| `/moat-retract` | Propagates a withdrawn number through every store in one pass, including what it actually was and what was built on it. |

`skills/moat/references/incidents.md` holds the abstracted incident record these
rules were paid for. Read it when a rule looks like pedantry.

## Install

Claude Code:

```
/plugin marketplace add kuromook/moat
/plugin install moat@moat
```

Any other skill-capable agent: copy `plugins/moat/skills/moat/SKILL.md` into the
project, or point the agent at it as a skill.

## What this is not

- **Not a methodology course.** Every rule is operational: it names the artefact
  to write or the arm to add.
- **Not for feature work.** Measurement code and reported numbers only. The test
  is whether anything you say would change if the result came out the other way.
- **Not a statistics library.** It never computes the number for you. It decides
  what has to exist before the number is allowed to mean something.

## Where it comes from

One long-running image-research project kept a ledger of its own failures. The
striking thing about that record is what is *not* in it: almost nothing was lost
to writing too much code, and almost everything was lost to a number travelling
without its quantity, a control that could not fail, or an instrument measuring
itself. The rules here are that ledger, generalised, with the project's own
specifics removed.

MIT licensed. Issues and corrections welcome — especially an incident that a
rule here would not have caught.
