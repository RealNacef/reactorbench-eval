# ReactorBench Core-20 — Three-Model Evaluation Protocol v1.0

## Objective

Evaluate 3 independently developed general-purpose LLMs on the same 20 advanced-nuclear
engineering prompts, producing 60 model responses for blinded expert annotation with
ReactorBench-Eval Rubric v0.1.

This is a compact cross-provider engineering evaluation, **not a definitive model leaderboard**.

## Core-20 composition

- 4 SMR / AMR / MMR tasks
- 5 GIF Gen-IV tasks
- 5 EPR / PWR systems & safety tasks
- 3 NOG / operating-procedure tasks
- 3 systems / replication / digital-twin tasks

The selected prompts emphasize areas with high discriminative value:
technology-family distinctions, safety functions, boundary conditions, system interfaces,
maturity claims, procedure validation and uncertainty.

## Models

Run one current/pinned model from each provider:

- Provider O: OpenAI — `gpt-5.6`
- Provider A: Anthropic — `claude-opus-4-1-20250805`
- Provider G: Google — `gemini-3.6-flash`

Record the exact model string actually accepted by each API at run time.

## Generation controls

For every run:

- single-turn / stateless request;
- identical system prompt;
- identical user prompt;
- no web search;
- no retrieval/RAG;
- no external tools;
- no reference context supplied to the model;
- provider-default sampling / reasoning settings;
- maximum output sized for a concise answer;
- exactly one response per model per prompt in the baseline study.

Do not manually edit model responses.

## Why provider defaults?

Current model families do not expose identical sampling/reasoning controls.
For the first baseline, use each provider's default behavior rather than forcing apparently
equivalent settings that are not actually equivalent. Record all settings you do override.

## Output limit

The system prompt requests roughly 100–180 words.
Do not truncate a response after generation solely to enforce this range.

## Blinding

The generation script creates a randomized private map:

`blind_code -> provider/model`

Label Studio tasks contain only a blind code, not the provider/model name.
Do not open the private mapping until the 60 annotations are complete.

## Annotation

Use ReactorBench-Eval Rubric v0.1 unchanged.

For each of the 60 responses, annotate:

- Technical Correctness
- Evidence Grounding
- Completeness
- Assumptions & Uncertainty
- Systems / Interface Reasoning
- Clarity
- Error Taxonomy
- Critical Failure
- Severity
- Verdict
- Review Path
- Written Rationale
- Improved Expert Answer
- Reviewer Confidence

## Analysis metrics

Primary:
- mean score by dimension and model;
- verdict distribution;
- Reject rate;
- Critical Failure rate;
- error-taxonomy frequency.

Secondary:
- performance by domain;
- performance by task difficulty;
- model wins per prompt after pairwise comparison;
- annotation time.

## Integrity rules

- Reference context is evaluator-only.
- Never alter a model response before annotation.
- If an API refuses or safety-filters a prompt, record the refusal as the actual model response.
- If a request fails technically, retry the same request without changing the prompt.
- Record retries and API errors separately.
- Keep provider/model mapping private during annotation.

## Optional robustness check after baseline

After the 60 baseline annotations, rerun the 5 hardest prompts once per model.
This gives a small 15-response stability sample without doubling the whole study.
