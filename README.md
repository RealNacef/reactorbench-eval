# ReactorBench-Eval

**Expert LLM evaluation for SMR/AMR/MMR, GIF Gen-IV, EPR/PWR systems,
nuclear operating procedures and systems engineering.**

## What this project demonstrates

- domain-specific prompt and benchmark design;
- Label Studio expert-annotation workflow;
- multidimensional model evaluation;
- technical critique and corrected reference answers;
- blinded cross-provider comparison;
- pairwise preference workflow and score-derived candidate pairs;
- error taxonomy and review-path labeling;
- independent nuclear-expert review and formal adjudication.

## Core-20 benchmark

The benchmark contains **20 prompts and 60 first-response outputs** collected from
ChatGPT Web, Claude Web and Gemini Web under a standardized no-tools/no-web protocol.

### Adjudicated results

| Interface | Overall | Technical | Grounding | Accept | Minor | Major | Reject |
|---|---:|---:|---:|---:|---:|---:|---:|
| ChatGPT Web | 4.94 | 5.00 | 4.95 | 18 | 2 | 0 | 0 |
| Gemini Web | 4.45 | 4.60 | 4.25 | 4 | 16 | 0 | 0 |
| Claude Web | 4.42 | 4.30 | 3.90 | 1 | 19 | 0 | 0 |

These are domain-specific consumer-UI results, not a general-purpose model leaderboard.

## Method

Each response is scored from 1–5 on:

1. Technical Correctness
2. Evidence Grounding
3. Completeness
4. Assumptions & Uncertainty
5. Systems / Interface Reasoning
6. Clarity & Usefulness

The rubric also captures overall disposition, severity, error taxonomy,
critical failures, review path, written rationale and an improved expert answer.

## Validation

The 60-response primary annotation set used an AI-assisted first pass followed by project-owner
expert sign-off. A second nuclear-systems expert independently re-annotated a **12-response
blinded subset**.

Pre-adjudication exact agreement was **41.7% for overall disposition** and **58.3% for severity**.
The 1–5 technical dimensions were generally much closer than the categorical thresholds.

All categorical disagreements were reviewed through a formal adjudication step. Original
annotations were preserved, and adjudicated labels were stored separately rather than
overwriting either reviewer's judgment.

See `validation/` for the complete traceability record.

## Limitations

- consumer web interfaces rather than pinned API snapshots;
- one run per model/prompt;
- compact 20-prompt domain benchmark;
- small 12-case independent-review subset;
- results are domain-specific, not a general model leaderboard.

## Safety

Only public and synthetic safety-oriented material is included. No proprietary,
classified or detailed security-sensitive nuclear information is used.


## Pairwise status

The current pairwise files are **score-derived candidate comparisons**, not an independently
human-labeled preference dataset. They are retained as the next-stage annotation queue.
Do not describe them as RLHF/preference-training data until the pairwise choices have been
reviewed directly by a human expert.
