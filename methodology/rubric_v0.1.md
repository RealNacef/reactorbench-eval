# ReactorBench-Eval Rubric v0.1

**Status:** Frozen after 6-task pilot calibration  
**Purpose:** Expert evaluation of LLM outputs across SMR/AMR/MMR, GIF Gen-IV, EPR/PWR systems and safety, NOG/operating procedures, systems engineering, replication, digital twin and AWP.

---

## 1. Core annotation principle

Score the **candidate response itself**, against the prompt and authoritative reference context.

Keep these four judgments separate:

1. **Verdict** — how much correction is needed before the response is usable?
2. **Severity** — what is the plausible consequence of the identified defect if acted upon?
3. **Dimension scores** — how well does the response perform on each independent quality dimension?
4. **Review path** — what additional expert or validation route is needed to make the answer usable?

A response may be:
- clearly written but technically wrong;
- factually correct but poorly grounded;
- incomplete but not dangerous;
- fundamentally wrong without being a "critical failure".

Do not let one bad dimension automatically force all other scores to 1.

---

# 2. Overall Verdict

## Accept as written

Use when the response is technically correct, sufficiently complete for the prompt,
appropriately grounded and calibrated, and does not require a material technical correction.

Minor stylistic edits that do not change meaning are allowed.

**Typical score pattern:** mostly 4–5.  
**Critical failure:** None.  
**Typical severity:** Low.

---

## Accept with minor edits

Use when the central answer is correct and usable, but a limited precision,
qualification, completeness, wording, or source-strength improvement is needed.

The correction must **not** change the central conclusion or technical approach.

Examples:
- missing one useful qualification;
- slightly weak wording;
- incomplete source hierarchy;
- small omission that does not alter the engineering conclusion.

**Typical score pattern:** mostly 3–5, with Technical Correctness normally >= 4.  
**Critical failure:** None.  
**Typical severity:** Low or Moderate.

---

## Major revision required

Use when there is a **material technical error or omission**, but the answer's central
approach remains recoverable without replacing the reasoning from scratch.

Examples:
- correct general direction but missing boundary conditions;
- technically plausible conclusion without uncertainty treatment;
- incomplete system/interface reasoning;
- procedure answer missing a material validation step;
- partially correct deployment assessment built on insufficient factors.

**Typical score pattern:** at least one material dimension around 1–3.  
**Critical failure:** normally None.  
**Typical severity:** Moderate or High.

---

## Reject

Use when the central claim, reasoning approach, or engineering recommendation is
fundamentally wrong, misleading, or unusable without replacing the core reasoning.

Examples:
- denying a relevant safety function;
- asserting perfect mixing where local dilution matters;
- treating a vendor schedule as sufficient proof of readiness;
- recommending continued operation based on an unverified indication;
- fundamental confusion between reactor technology families.

**Important:** Reject does **not** automatically mean Critical severity.

**Typical score pattern:** Technical Correctness usually 1–2.  
**Clarity may still be 4–5 if the wrong answer is clearly written.**

---

# 3. Severity

Severity is the **consequence of the defect**, not a synonym for the verdict.

Judge the plausible consequence if the response were used for its intended engineering
or decision-support purpose.

## Low

The defect is mainly stylistic, terminological, or a minor precision issue.

It would not materially alter a technical or programme decision.

Examples:
- minor wording weakness;
- small non-material omission;
- unnecessary verbosity.

---

## Moderate

The defect could mislead an engineer, analyst, technology-screening exercise,
or project decision, but is likely reversible and would normally be caught by routine review.

Examples:
- weak technology-maturity assessment;
- incomplete deployment-readiness reasoning;
- incorrect source hierarchy;
- non-safety-significant interface omission.

---

## High

The defect could materially affect a safety, design, operating, licensing,
configuration, or major programme decision if acted upon.

Examples:
- omission of LOCA boundary conditions;
- incorrect treatment of a credited heat-removal function;
- incorrect procedure-validation logic;
- material reactor-physics error;
- major interface/configuration omission.

---

## Critical

Reserve for defects capable of producing severe or immediate consequences,
or for a defined **Critical Failure**.

Examples:
- direct false safety assurance in a safety-significant decision;
- unsafe operator recommendation in a consequential plant state;
- invented mandatory regulatory requirement used as authority;
- fundamental physics error that directly supports an unsafe conclusion.

### Consistency rule

**Critical severity requires a non-"None" Critical Failure.**

A response can be Reject + High + Critical Failure=None.

---

# 4. Dimension Scores

Use each dimension **independently**.

## 4.1 Technical Correctness

**1 — Fundamentally wrong:** central scientific/engineering claim is false.  
**2 — Major weakness:** substantial technical error, but some valid content exists.  
**3 — Partly correct:** core idea is plausible/correct, with material limitations.  
**4 — Correct with minor gaps:** technically sound; only small precision issues.  
**5 — Expert-quality:** technically correct, precise, appropriately qualified.

---

## 4.2 Evidence Grounding

This score is about alignment with the supplied authoritative basis.
It is **not simply a citation-presence score**.

**1 — Contradicts or ignores the authoritative basis; relies on unsupported authority.**  
**2 — Weakly grounded; important claims are unsupported or evidence hierarchy is wrong.**  
**3 — Partially grounded; main claim has support but evidence use is incomplete.**  
**4 — Well grounded with minor sourcing/provenance gaps.**  
**5 — Strongly traceable to the supplied basis and appropriately distinguishes source authority.**

If the prompt does not require explicit citations, do not penalize the response merely
for lacking citation formatting.

---

## 4.3 Completeness

Judge only what is **material to answering the prompt**.

**1 — Misses the central required elements.**  
**2 — Covers a small portion but omits major required elements.**  
**3 — Covers the core answer but misses one or more material elements.**  
**4 — Sufficiently complete; minor omission only.**  
**5 — Complete and appropriately scoped without unnecessary expansion.**

---

## 4.4 Assumptions & Uncertainty

Do not require an uncertainty paragraph on every factual question.
Judge whether the response is **appropriately calibrated for the task**.

**1 — Unjustified certainty or ignores decision-critical assumptions/boundaries.**  
**2 — Important assumptions or uncertainty are substantially missing.**  
**3 — Some calibration is present but incomplete.**  
**4 — Appropriate assumptions/limits are identified with minor gaps.**  
**5 — Excellent calibration; clearly distinguishes facts, assumptions, variability,
uncertainty and decision limits when relevant.**

For a simple factual task with no material uncertainty, a concise appropriately bounded
answer may receive 4–5.

---

## 4.5 Systems / Interface Reasoning

Judge whether the answer recognizes the relevant system boundary and dependencies.

**1 — Ignores or contradicts material interfaces/dependencies.**  
**2 — Recognizes limited interactions but misses major dependencies.**  
**3 — Adequate system view with one or more material gaps.**  
**4 — Strong interface/system reasoning with minor omissions.**  
**5 — Excellent system-level reasoning, including relevant dependencies, states,
interfaces and downstream impacts.**

For a narrow factual question, 4–5 is possible if no deeper interface reasoning is required
and the answer stays correctly scoped.

---

## 4.6 Clarity & Usefulness

**Score writing quality independently from technical correctness.**

**1 — Very difficult to understand, internally incoherent, or unusable.**  
**2 — Understandable only with effort; poorly organized or ambiguous.**  
**3 — Generally understandable but inefficient or imprecise.**  
**4 — Clear, concise and easy to follow.**  
**5 — Exceptionally clear, structured, precise and directly useful.**

A confidently written false statement can score:
- Technical Correctness = 1
- Clarity = 4 or 5

Do not use Clarity=1 simply because the answer is wrong.

---

# 5. Error Taxonomy

Select the **smallest set of root-cause labels** that explains the defect.
Usually 1–3 labels are enough.

## No material error
Use only when no other error label applies.

## Factual or scientific error
A direct technical/scientific statement is false.

Do not apply automatically to every bad answer if a more specific reasoning or
governance error is the true issue.

## Unsupported generalization
The response extrapolates beyond the evidence, design, technology family, operating
state or applicable context.

## Source or authority weakness
The response relies on the wrong source hierarchy, treats a weak source as authoritative,
or fails to resolve source applicability/revision.

## Technology-family confusion
The response conflates reactor families or attributes one technology's characteristics
to another.

## Safety-function omission
A material safety function, credited function or relevant protection mechanism is omitted,
denied or misrepresented.

## Interface or system-boundary omission
The response ignores material upstream/downstream systems, support functions,
shared resources, interfaces or configuration impacts.

## Incorrect operating-state assumption
The answer assumes an operating state or plant condition inconsistent with the task.

## Missing initial or boundary condition
Decision-critical starting conditions, boundary conditions or scenario definitions are missing.

## Uncertainty or sensitivity omitted
The answer fails to address uncertainty, variability, model limitation or sensitivity when
these could change the conclusion.

## Requirements-traceability failure
The answer uses an ambiguous/unverifiable requirement or does not connect a conclusion
to an approved requirement or technical basis.

## Procedure or operator-action defect
The answer recommends or accepts ambiguous, unvalidated or inappropriate operator actions,
procedure logic, indications or sequencing.

## FOAK-NOAK or maturity overclaim
The response overstates design maturity, replication readiness, learning assumptions,
standardization or FOAK-to-NOAK transferability.

## Economic or deployment overclaim
The response makes an unjustified claim about cost, schedule, readiness, financing,
supply chain or deployment feasibility.

## Incorrect escalation or review path
The response fails to identify the additional technical, safety, operations, source,
or interface review needed to support the conclusion.

## Unclear or poorly structured
Use only for a genuine communication/organization defect.
Do **not** use merely because the answer is technically wrong.

## Other
Use sparingly and describe the missing category in the written rationale.

---

# 6. Critical Failure

A Critical Failure is **not simply a severe error**.
It is a defined failure mode that can override otherwise reasonable sub-scores.

## None
No defined critical failure.

## False safety assurance
The response asserts safety/acceptability despite missing or contradictory evidence
in a safety-significant context.

## Invented authoritative requirement
The response fabricates or falsely attributes a mandatory regulatory/design requirement.

## Fundamental reactor-physics error
A basic neutronic/reactor-physics error directly invalidates the safety or engineering conclusion.

Use only for genuinely fundamental errors, not every reactor-physics imprecision.

## Unsafe operating-procedure recommendation
The response recommends an operator action or continuation logic that could create
a material safety risk.

## Major technology-family misclassification
Use only when the misclassification materially changes the engineering, safety,
fuel-cycle or deployment conclusion.

## Other critical failure
Requires explicit written justification.

### Consistency rules

If Critical Failure != None:
- Verdict should normally be **Reject**.
- Severity should be **Critical**.
- Written rationale must explicitly explain the failure mechanism.

---

# 7. Review Path

Review Path answers:

**"What additional review or validation is required before this answer could be relied upon?"**

It is not the same as reviewer confidence.

## No additional review
Use only when:
- Accept as written; or
- a genuinely minor editorial correction is sufficient.

Do not normally use this for High-severity Major Revision or Reject cases.

## Domain SME review
Use when specialist technical expertise is needed to validate/correct the answer.

Examples: reactor physics, materials, SMR maturity, fuel cycle.

## Systems or interface review
Use when the defect concerns system boundaries, shared functions, supporting systems,
configuration or multidisciplinary interfaces.

## Independent safety review
Use when the conclusion is safety-significant or depends on accident/safety analysis.

Examples: LOCA, recriticality, credited safety function.

## Operations or procedure validation
Use for NOG/procedure, operator action, simulator validation, human-factors or operating
sequence questions.

## Source verification required
Use when the key uncertainty is provenance, authority, design revision or conflicting evidence.

### Selection rule

Choose the **primary next review action**, not every possibly relevant reviewer.

---

# 8. Written Rationale

The rationale is mandatory and is a core benchmark output.

Do not enter:
- "-"
- "wrong answer"
- "lack of knowledge"
- "needs more detail"

Recommended length: **40–100 words**.

Use this structure:

1. **Judgment:** State the overall problem.
2. **Valid element:** Note any part that is correct, if applicable.
3. **Material defect:** Identify the main error/omission.
4. **Evidence link:** Explain how it conflicts with the reference context.
5. **Consequence / correction:** Explain why it matters and what needs to change.

Example:

> The response correctly recognizes peak temperature as an important LOCA acceptance
> parameter, but it treats that result as sufficient to support the safety conclusion.
> It omits the initiating-event assumptions, boundary conditions, safety-system availability
> and uncertainty treatment required to interpret the calculation. These omissions prevent
> the reviewer from checking whether the result applies to the analysed scenario. Major
> revision and independent safety review are therefore required.

---

# 9. Improved Expert Answer

Purpose: provide the corrected, safe, concise reference-quality answer.

Recommended length: **50–140 words**, unless the prompt clearly calls for shorter output.

The improved answer must:
- correct every material defect named in the rationale;
- remain within the supplied reference context or verified public basis;
- avoid introducing proprietary or unnecessary sensitive information;
- include assumptions/uncertainty only when relevant;
- preserve appropriate system boundaries;
- state review/escalation needs when they are part of the technical answer.

Do not simply copy the reference context verbatim unless that is genuinely the best answer.

---

# 10. Reviewer Confidence

Reviewer confidence measures confidence in **your annotation**, not confidence in the model answer.

## 1 — Very low
The task is outside the reviewer's competence or the reference basis is insufficient.

## 2 — Low
Material uncertainty remains; specialist verification is strongly needed.

## 3 — Moderate
Reasonable judgment, but some technical/source uncertainty remains.

## 4 — High
Strong competence and adequate reference basis; limited residual uncertainty.

## 5 — Very high
Direct expertise and clear authoritative basis; the annotation is unlikely to change after review.

Do not use 5 simply because the candidate answer is obviously poor.

---

# 11. Cross-field Consistency Rules

Use these as automatic QA checks.

1. **Accept as written**
   - Critical Failure = None
   - normally no material error
   - Technical Correctness >= 4
   - Evidence Grounding >= 4

2. **Accept with minor edits**
   - Critical Failure = None
   - Technical Correctness normally >= 4
   - Severity normally Low or Moderate

3. **Major revision required**
   - at least one material dimension normally <= 3
   - Severity typically Moderate or High

4. **Reject**
   - central reasoning/claim unusable
   - Technical Correctness normally <= 2
   - Clarity can still be 4–5

5. **Critical severity**
   - Critical Failure must not be None

6. **Critical Failure != None**
   - Verdict normally Reject
   - rationale explicitly explains why

7. **High-severity or Reject answer**
   - "No additional review" should be exceptional and justified

8. **No material error**
   - cannot coexist with another error taxonomy label

9. **Unclear or poorly structured**
   - requires an actual clarity/structure problem
   - do not use as a proxy for technical wrongness

10. **Written rationale**
    - mandatory; no placeholder

---

# 12. Annotation Order

To reduce anchoring and improve consistency, annotate in this order:

1. Read prompt and reference context.
2. Read candidate response once.
3. Assign Technical Correctness.
4. Assign Evidence Grounding.
5. Assign Completeness.
6. Assign Assumptions & Uncertainty.
7. Assign Systems / Interface Reasoning.
8. Assign Clarity.
9. Select Error Taxonomy.
10. Decide Critical Failure.
11. Decide Severity.
12. Decide Overall Verdict.
13. Select Review Path.
14. Write Rationale.
15. Write Improved Expert Answer.
16. Set Reviewer Confidence.
17. Perform final consistency check.

This order prevents an early "Reject" decision from forcing every sub-score downward.

---

# 13. Pilot Calibration Notes

The 6-task pilot showed four calibration issues that v0.1 corrects:

- **Clarity was coupled too strongly to correctness.**
- **High severity was used for every pilot defect, including programme/deployment cases.**
- **"No additional review" was selected on several High-severity rejected answers.**
- **Written rationales were missing or placeholders on most completed tasks.**

These issues must be corrected before scaling to the full seed benchmark.

---

# 14. Versioning

This document is **ReactorBench-Eval Rubric v0.1**.

Freeze it before the next annotation batch.

If a rule changes:
- do not silently edit v0.1;
- create v0.2;
- record date, reason, affected fields and whether earlier annotations need re-review.

Recommended changelog format:

| Version | Date | Change | Reason | Re-annotation required? |
|---|---|---|---|---|
| v0.1 | 2026-08-15 | Pilot-calibrated initial rubric | 6-task pilot audit | Yes — pilot 6 |
