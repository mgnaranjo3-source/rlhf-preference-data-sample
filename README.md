# RLHF Preference Data Sample

A small, fully documented example of **human preference data**: the pairwise comparisons used in Reinforcement Learning from Human Feedback (RLHF) and similar techniques to teach a model which responses people prefer.

> Every prompt and response here is **synthetic**, written for demonstration. Nothing comes from any real project or platform.

## Contents
| File | Purpose |
|---|---|
| [`data/preference_pairs.jsonl`](data/preference_pairs.jsonl) | 8 preference records (EN and ES) in a common JSONL format |
| [`schema.md`](schema.md) | Field-by-field description of each record |
| [`labeling-guide.md`](labeling-guide.md) | How the preferred response was selected, with tie and skip rules |

## Record example
```json
{"id": "pp-001", "prompt": "...", "response_a": "...", "response_b": "...", "preference": "A", "strength": 3, "deciding_factor": "accuracy", "rationale": "...", "language": "en", "flags": []}
```

## What the sample covers
- accuracy errors (wrong numbers, wrong facts)
- instruction-following failures (wrong language, ignored length limit)
- an unnecessary refusal vs. a helpful answer
- a safety-critical case (possible medical emergency)
- a genuine tie

## License
MIT
