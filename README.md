# ReactorBench-Eval

**Expert LLM evaluation for SMR/AMR/MMR, GIF Gen-IV, EPR/PWR systems,
nuclear operating procedures and systems engineering.**

## What this project demonstrates

- domain-specific prompt and benchmark design;
- Label Studio expert-annotation workflow;
- multidimensional model evaluation;
- technical critique and corrected reference answers;
- blinded cross-provider comparison;
- pairwise preference data;
- error taxonomy and review-path labeling;
- independent-review pack for inter-annotator agreement.

## Core-20 benchmark

The benchmark contains 20 prompts and 60 first-response outputs collected from
ChatGPT Web, Claude Web and Gemini Web using a standardized no-tools/no-web protocol.

| Interface | Overall | Technical | Grounding | Accept/Minor | Major/Reject |
|---|---:|---:|---:|---:|---:|
| ChatGPT Web | 4.97 | 5.00 | 5.00 | 100% | 0% |
| Gemini Web | 4.45 | 4.60 | 4.25 | 100% | 0% |
| Claude Web | 4.38 | 4.25 | 3.85 | 95% | 5% |

## Repository structure

```text
methodology/
data/
results/
charts/
label-studio/
docs/
```

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

## Important validation status

The current 60-response labels are **assistant-drafted expert evaluations pending
project-owner sign-off**. A separate 12-task independent-review pack is included
to measure inter-annotator agreement before any claim of a fully human-validated benchmark.

## Limitations

- consumer web interfaces rather than pinned API snapshots;
- one run per model/prompt;
- compact 20-prompt domain benchmark;
- results are domain-specific, not a general model leaderboard.

## Safety

Only public and synthetic safety-oriented material is included. No proprietary,
classified or detailed security-sensitive nuclear information is used.
