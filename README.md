# When “Neutral” Isn’t Neutral

## A human-in-the-loop AI evaluation portfolio

> “The replacement arrived the day after I left for my trip.”

The AI grader labelled that sentence **Neutral / Clear / High**. I disagreed.

The replacement arrived too late to help before the trip. That timing implies a negative experience, even though the customer never directly states how they feel. My final reference was **Negative / Needs Review / Medium**.

That disagreement is at the heart of this project. I built a repeatable evaluation around 18 synthetic customer-support messages to see where an AI sentiment grader was reliable, where it was uncertain, and where a human needed to make the final decision.

## What I tested

The test set included straightforward messages as well as cases involving:

- Sarcasm.
- Mixed praise and criticism.
- Polite dissatisfaction.
- Negation.
- Implied emotion.
- Short or ambiguous wording.

I wrote the human reference answers before testing the grader. Each case included a sentiment label, review status, confidence level, supporting evidence, and version information.

The grader received the same prompt and rubric for every case. Each message was tested in a fresh ChatGPT Work conversation so that earlier answers could not affect later ones.

![Diagram showing the grader setup and the information supplied for one test case](guide/grader-setup-and-test-input.svg)

## What happened

| Measure | Agreement | Rate |
|---|---:|---:|
| Sentiment label | 17/18 | 94.4% |
| Review status | 17/18 | 94.4% |
| Confidence | 15/18 | 83.3% |
| Label, status, and confidence combined | 15/18 | 83.3% |

The agreement score was only the beginning.

Five cases differed from the human references in at least one field. I reviewed each disagreement instead of assuming that either the human or the AI must be right.

That review produced two different kinds of findings:

- In two cases, the grader’s confidence rating was better supported. I revised the human reference rather than treating the grader as wrong.
- In one case, the grader missed a meaningful implied negative experience. I preserved that failure as a regression case for future retesting.

All 18 grader explanations were grounded in the supplied messages. The small test showed that the grader could usually follow the rubric, but it also showed why a high agreement rate does not remove the need for human review.

## Repository guide

### User guide

[**Read the complete user guide**](guide/human-in-the-loop-sentiment-evaluation.md)

The guide walks through the full evaluation process, from defining the client's question to reporting the results. It includes the worked HC-006 failure and is written for a capable beginner.

---

### Files

| File | What it contains |
|---|---|
| [Sentiment rubric](evals/sentiment-rubric.md) | The labels, decision rules, review-status rules, and confidence guidance. |
| [Human reference set](data/human-reference-set.md) | All 18 synthetic messages and their human-approved answers. |
| [Validation summary](results/validation-summary.md) | The testing method, agreement results, findings, and limitations. |
| [Disagreement log](results/disagreement-log.md) | The five differences and how each one was resolved. |
| [Regression case](results/regression-case.md) | The grader failure retained for future testing. |
| [Grader setup diagram](guide/grader-setup-and-test-input.svg) | The information supplied to the grader for one test case. |

## Why the human review matters

A disagreement does not automatically mean that the AI is wrong. It may reveal an inconsistent human answer, an unclear rule, missing context, a grader error, or a genuinely difficult case.

The useful part of evaluation is finding out which one happened.

This project keeps the original human and grader answers visible, records the reasoning behind every final decision, and separates corrected human references from AI failures that should be tested again.

## Limits

- This is a small practice evaluation using synthetic messages, not client or production data.
- The grader was tested manually through ChatGPT Work without API sampling controls or a fixed model snapshot.
- The results describe one practice baseline on 18 cases. They are not formal model validation.
- The retained regression case has not yet been rerun after a meaningful grader, prompt, or rubric change.

## Skills demonstrated

Rubric writing, test-case design, human labeling, AI-response evaluation, evidence-based adjudication, error analysis, regression planning, technical writing, and versioned documentation.

Created by Jill Flanagan.
