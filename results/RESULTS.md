# Results — Adjudicated Core-20 v0.1

## Dataset

- 20 advanced-nuclear engineering prompts
- 3 consumer-model interfaces
- 60 first-response outputs
- 6 rubric dimensions
- 12-response independent-review subset
- 9 formally adjudicated categorical disagreements

## Final adjudicated aggregate

| Interface | Overall | Technical | Grounding | Accept | Minor | Major | Reject |
|---|---:|---:|---:|---:|---:|---:|---:|
| ChatGPT Web | 4.94 | 5.00 | 4.95 | 18 | 2 | 0 | 0 |
| Gemini Web | 4.45 | 4.60 | 4.25 | 4 | 16 | 0 | 0 |
| Claude Web | 4.42 | 4.30 | 3.90 | 1 | 19 | 0 | 0 |

## Validation

Independent review exposed a real calibration difference around the boundary between
`Accept as written` and `Accept with minor edits`. Pre-adjudication agreement metrics are
reported as-is and are not recalculated after consensus.

Final benchmark labels follow this hierarchy:

1. independent agreement where both reviewers matched;
2. formal adjudication where they disagreed;
3. signed-off primary annotation for cases outside the 12-response review subset.

## Interpretation boundary

These results should not be treated as a universal model leaderboard. They measure a small,
domain-specific consumer-UI benchmark under one standardized first-response protocol.
