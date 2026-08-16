# Independent Reviewer Validation — Core-20

## Scope

A second nuclear-systems expert independently annotated **12 blinded model responses**
using ReactorBench-Eval Rubric v0.1.

The primary annotation set used here for comparison is the project owner's AI-assisted
first-pass set. These metrics therefore measure **reviewer calibration / validation**, not
agreement between two fully independent unaided human annotations.

## Agreement snapshot

- Verdict exact agreement: **41.7%**
- Verdict Cohen's kappa: **0.034**
- Verdict quadratic-weighted kappa: **-0.053**
- Severity exact agreement: **58.3%**
- Severity Cohen's kappa: **0.0**
- Severity quadratic-weighted kappa: **0.0**

The low kappa values should not be hidden. The 12-case sample is small and highly skewed
toward acceptable responses, so chance-corrected kappa is unstable and exposes a real
calibration difference: the second reviewer tends to use **Accept as written / Low**
more often, while the primary rubric pass more often uses **Accept with minor edits**.

## 1–5 rating agreement

| Dimension | Exact | Within ±1 | Mean absolute difference |
|---|---:|---:|---:|
| Technical Correctness | 50.0% | 91.7% | 0.58 |
| Evidence Grounding | 58.3% | 83.3% | 0.58 |
| Completeness | 75.0% | 100.0% | 0.25 |
| Uncertainty Calibration | 75.0% | 100.0% | 0.25 |
| Systems Reasoning | 75.0% | 100.0% | 0.25 |
| Clarity | 33.3% | 100.0% | 0.67 |

## Main adjudication case

The largest categorical disagreement is **RB-EPR-004 / Model-B**:

- Primary pass: **Major revision required / High**
- Independent reviewer: **Accept as written / Low**

This case should be manually adjudicated before publishing final benchmark metrics.
The remaining disagreements are mostly one-step calibration differences between
`Accept as written` and `Accept with minor edits`, or `Low` versus `Moderate`.

## Recommended portfolio wording

Do not claim "high inter-annotator agreement" from this sample.

A defensible statement is:

> An independent nuclear-systems reviewer re-annotated a 12-response blinded subset.
> Exact agreement was 41.7% on overall disposition and
> 58.3% on severity; 1–5 rubric dimensions were generally
> within one point, with remaining disagreements used for rubric adjudication.

## Next action

1. Adjudicate the largest disagreement.
2. Review the remaining one-step verdict/severity disagreements.
3. Store the adjudicated label separately rather than overwriting either reviewer's original label.
4. Recompute final agreement metrics after documenting adjudication.
