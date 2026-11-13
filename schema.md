# Record Schema

One JSON object per line (`.jsonl`).

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | string | yes | Unique record id, e.g. `pp-001` |
| `prompt` | string | yes | The user message both responses answer |
| `response_a` | string | yes | First candidate response |
| `response_b` | string | yes | Second candidate response |
| `preference` | `"A"`, `"B"` or `"tie"` | yes | Which response is better overall |
| `strength` | integer 0–3 | yes | 0 = tie, 1 = slightly better, 2 = better, 3 = much better |
| `deciding_factor` | string | yes | One of `accuracy`, `instruction_following`, `helpfulness`, `safety`, `concision`, `none` |
| `rationale` | string | yes | 1–4 sentences, specific, pointing to the exact text |
| `language` | `"en"`, `"es"` or `"mixed"` | yes | Language of the prompt |
| `flags` | array of strings | yes | Notable issues, e.g. `["unnecessary_refusal"]`; empty if none |

## Consistency rules
- `preference = "tie"` if and only if `strength = 0` and `deciding_factor = "none"`.
- `strength = 3` requires a critical failure in the losing response: a misleading factual error, a safety issue, an ignored core instruction, or an unnecessary refusal.
