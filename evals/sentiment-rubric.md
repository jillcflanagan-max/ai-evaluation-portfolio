# Sentiment Evaluation Rubric

- Version: 1.0
- Status: Practice baseline
- Scope: Short customer messages

## Evaluation target

Follow the project's stated evaluation target. A project may ask for sentiment about the complete experience, a specific aspect, the process, or the final outcome.

If no target is supplied:

- Evaluate the overall sentiment across the complete message.
- Do not assume that the final sentence is automatically the most important.
- Count past and present sentiment when both are meaningfully expressed.
- Use **Mixed** when meaningful positive and negative sentiment are both present and neither clearly dominates.
- Use a single label when the message clearly emphasizes one sentiment.
- Use **Needs Review** when the correct label depends on an evaluation target that has not been defined.

## Sentiment labels

### Positive

The message expresses an overall favourable attitude, satisfaction, appreciation, enthusiasm, hope, or approval.

### Negative

The message expresses an overall unfavourable attitude, dissatisfaction, criticism, disappointment, frustration, anger, or pessimism.

### Neutral

The message is primarily factual, procedural, descriptive, or informational and does not express meaningful positive or negative sentiment.

Neutral does not mean unclear or mixed.

### Mixed

The message contains meaningful positive and negative sentiment, and neither clearly dominates.

If one sentiment clearly dominates, use Positive or Negative and explain the secondary sentiment in the evidence.

## Review status

Record one review status in addition to the sentiment label:

- **Clear:** The text and available context support a reliable decision.
- **Needs Review:** The message is ambiguous, context-dependent, sarcastic, contradictory, extremely short, or cannot be labeled reliably without human judgment.

Needs Review is not a sentiment label. When the information does not support any label, record **Unassigned** with **Needs Review**. Unassigned is a temporary workflow state.

## Confidence

- **High:** The sentiment is direct and unambiguous.
- **Medium:** The decision is reasonable, but some interpretation is required.
- **Low:** Important ambiguity or missing context could change the decision.

Low-confidence cases should normally receive Needs Review.

## Evidence rules

For every decision:

- Identify the words, phrases, or context supporting the label.
- Consider the entire message rather than isolated sentiment words.
- Explain the effect of negation, sarcasm, contrast, or mixed language.
- Do not infer sentiment from a factual statement alone.
- Do not invent missing context.

## Three-label projects

If a project allows only Positive, Neutral, and Negative:

- Map a mixed message to Positive or Negative only when one clearly dominates.
- Do not automatically map a balanced mixed message to Neutral.
- Send balanced mixed or genuinely unclear cases for human review.
- Record the project-specific mapping rule before grading.
