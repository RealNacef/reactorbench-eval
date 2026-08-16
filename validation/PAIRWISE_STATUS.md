# Pairwise Validation Status

The existing Core-20 pairwise set was generated from the rubric-score ranking of model responses.
It is useful as a **candidate pair queue**, but it is not yet an independent human preference dataset.

Before using pairwise results in a CV or claiming RLHF/preference-data experience:

1. present each A/B pair without score/model identity;
2. have a human expert select the preferred response directly;
3. record preference strength and rationale;
4. preserve the score-derived preference separately;
5. compare direct preference vs score-derived ranking.

Recommended minimum for v0.1: 10 direct human-reviewed pairs.
