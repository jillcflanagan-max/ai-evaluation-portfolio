# Disagreement Review

Five differences between the grader and the human reference set were reviewed. Three involved confidence only. One human reference was strengthened, one was reduced, and one substantive grader failure was preserved for regression testing.

| Case | Difference | Review | Resolution |
|---|---|---|---|
| HL-001 | Human confidence Medium; grader High | The positive and negative statements are direct, but deciding that neither dominates requires interpretation. | Retained human Mixed / Clear / Medium. |
| HL-002 | Human confidence Medium; grader High | “Unfortunately” and “exactly the same problem” make the dissatisfaction clear despite the polite thanks. | Changed human confidence to High. |
| HC-006 | Human Negative / Needs Review / Medium; grader Neutral / Clear / High | The grader missed the inconvenience implied by a replacement arriving after the customer had left for a trip. | Retained the human reference and created REG-001. |
| HC-008 | Human confidence High; grader Medium | Both failure and recovery are explicit, but judging their overall balance requires interpretation. | Changed human confidence to Medium. |
| HC-009 | Human confidence Medium; grader High | Praise for the agent and criticism of the policy concern different targets; deciding the overall balance requires interpretation. | Retained human Mixed / Clear / Medium. |

## What the review showed

- Disagreement does not automatically mean the model is wrong.
- Confidence can reveal calibration problems even when the label is correct.
- Human references should be revisable when the evidence supports a change.
- Important resolved failures should be saved for later regression testing.
