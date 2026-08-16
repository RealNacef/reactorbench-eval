# Independent Reviewer Validation — Core-20

## Scope

A second nuclear-systems expert independently annotated **12 blinded model responses**
using ReactorBench-Eval Rubric v0.1.

The primary annotation set was an AI-assisted first pass signed off by the project owner.
The independent labels are preserved unchanged.

## Pre-adjudication agreement

- Verdict exact agreement: **41.7%**
- Verdict Cohen's kappa: **0.034**
- Severity exact agreement: **58.3%**
- Severity Cohen's kappa: **0.000**

The small, acceptance-skewed 12-case sample makes chance-corrected kappa unstable.
More importantly, it revealed a calibration difference: the independent reviewer used
`Accept as written / Low` more often, while the primary pass used
`Accept with minor edits / Moderate` more often.

### Important methodological note

The agreement metrics above remain **pre-adjudication metrics**. They are not recomputed
after consensus, because adjudication is intended to create final benchmark labels, not to
artificially inflate inter-reviewer agreement.

## Formal adjudication

All **9 categorical disagreements** were reviewed and an adjudicated label was recorded
separately in `ADJUDICATION_LOG_v0.1.csv`. Neither reviewer's original labels were overwritten.

The most important case was `RB-EPR-004 / Model-B` (heterogeneous boron dilution):

- Primary: `Major revision required / High`
- Independent reviewer: `Accept as written / Low`
- **Adjudicated: `Accept with minor edits / Moderate`**

The core physics was accepted. The correction is limited to qualifying/removing several
additional transient examples that were not supported by the controlled reference basis.

## Final benchmark-label policy

For the 12 independently reviewed cases, the adjudicated label is the final benchmark label.
For the remaining 48 cases, the signed-off primary label remains the final label.

This preserves:
1. primary annotation;
2. independent annotation;
3. adjudication;
4. final benchmark label

as separate traceable layers.
