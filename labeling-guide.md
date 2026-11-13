# Preference Labeling Guide

## Steps
1. Read the prompt and list what the user needs (explicit and implicit).
2. Evaluate each response on its own: accuracy, instruction following, safety, helpfulness, writing.
3. Find the **deciding factor**: the single difference that matters most to the user.
4. Set **strength** by how much that factor matters (see [`schema.md`](schema.md)).
5. Write the rationale: deciding factor first, point to the text, state the impact on the user.

## Priority order when responses trade off
1. **Safety**: an unsafe response loses.
2. **Accuracy**: a misleading error loses to a correct but plainer answer.
3. **Instruction following**: explicit constraints (language, length, format) matter.
4. **Helpfulness**: completeness and usefulness.
5. **Concision and style**: tie-breakers, not primary reasons.

## Ties
Use `tie` only when the differences are truly trivial or cancel out. A tie is a valid label, not a way to avoid deciding.

## Skip rules
Skip the item and report it if:
- the prompt contains real personal data;
- both responses are identical;
- a key fact can't be verified and it decides the comparison.
