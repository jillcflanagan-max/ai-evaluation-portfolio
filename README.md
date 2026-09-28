# Human-in-the-Loop AI Evaluation Portfolio

This practice project shows a small, traceable evaluation of an AI sentiment grader. It covers rubric design, synthetic test-case creation, human reference labels, grader comparison, disagreement review, and regression testing.

The goal was not to prove that a model was production-ready. The goal was to build a careful evaluation process, find where the grader disagreed with human judgment, and preserve an important failure for future retesting.

## What I did

- Wrote a sentiment rubric that separates the sentiment label from the need for human review.
- Created 18 synthetic practice cases, including sarcasm, mixed sentiment, polite dissatisfaction, negation, implied emotion, and short ambiguous messages.
- Recorded a human label, review status, confidence level, evidence, and version information for every case.
- Tested each case separately in a fresh ChatGPT Work conversation using the same grader prompt and rubric.
- Compared the grader with the human reference set.
- Reviewed five disagreements instead of automatically treating either side as correct.
- Changed two human confidence ratings when the grader's answer was better supported.
- Preserved one substantive grader failure as a regression case.

## Results

| Measure | Agreement | Rate |
|---|---:|---:|
| Sentiment label | 17/18 | 94.4% |
| Review status | 17/18 | 94.4% |
| Confidence | 15/18 | 83.3% |
| Label, status, and confidence combined | 15/18 | 83.3% |

All 18 grader explanations were grounded in the supplied message. One case exposed a meaningful weakness: the grader treated an inconvenient delivery time as a neutral fact and missed the implied negative experience.

## Repository guide

- [`guide/human-in-the-loop-sentiment-evaluation.md`](guide/human-in-the-loop-sentiment-evaluation.md) — Beginner-facing guide to the complete evaluation process, including the worked HC-006 failure.
- [`evals/sentiment-rubric.md`](evals/sentiment-rubric.md) — Label definitions, decision rules, review status, and confidence guidance.
- [`data/human-reference-set.md`](data/human-reference-set.md) — The 18 synthetic cases and human-approved references.
- [`results/validation-summary.md`](results/validation-summary.md) — Test method, results, and limitations.
- [`results/disagreement-log.md`](results/disagreement-log.md) — How the five differences were reviewed and resolved.
- [`results/regression-case.md`](results/regression-case.md) — The failure retained for future testing.

## Limits

- This is a small practice evaluation using synthetic messages, not client or production data.
- The grader was tested manually through ChatGPT Work without API sampling controls or a fixed model snapshot.
- The results describe one practice baseline on 18 cases. They are not formal model validation.
- The regression case has not yet been rerun after a meaningful grader or rubric change.

## Skills demonstrated

Rubric writing, test-case design, human labeling, AI-response evaluation, evidence-based adjudication, error analysis, regression planning, technical writing, and versioned documentation.

Created by Jill Flanagan.
