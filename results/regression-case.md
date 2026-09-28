# Regression Case REG-001

## Source case

**Message:** The replacement arrived the day after I left for my trip.

## Expected result

- Sentiment label: Negative
- Review status: Needs Review
- Confidence: Medium

## Original grader result

- Sentiment label: Neutral
- Review status: Clear
- Confidence: High

## Failure analysis

The grader treated the delivery timing as a factual statement and required explicit emotional language before assigning sentiment. The human review retained Negative because a replacement arriving after the person had already left for a trip reasonably implies that the replacement was not useful when needed.

Needs Review and Medium confidence were retained because the inconvenience is implied rather than directly stated.

## Why this case matters

This case tests whether a grader can recognize implied experience without inventing unsupported context. A better grader should detect the likely inconvenience while preserving uncertainty.

## Current status

Awaiting rerun after a meaningful grader, prompt, or rubric change.
