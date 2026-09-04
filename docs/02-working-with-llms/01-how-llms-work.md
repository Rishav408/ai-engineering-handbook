# 2.1 How LLMs Work

Before touching prompt engineering or RAG, you need the handful of core mechanics that every LLM interaction runs on. These three ideas show up in almost every other note in this repo.

## Core elements

**Tokens**
- Sub-word units the model reads and writes — roughly 4 characters ≈ 1 token in English
- Billing, context limits, and generation all happen at the token level, not the word or character level
- This is why a "10,000 word limit" doesn't map cleanly onto token counts — punctuation, whitespace, and rare words all tokenize differently

**Context**
- The full set of tokens visible to the model during a single inference call
- That's: system prompt + conversation history + retrieved data + current query, all combined
- See [2.3 Context Engineering](03-context-engineering.md) for how this gets managed in practice

**Sampling parameters**
- Settings that control how random or deterministic the next-token selection is during generation

## Sampling parameter reference

| Parameter | What it controls | Typical range | Effect |
|---|---|---|---|
| Temperature | Randomness of token probability distribution | 0.0 – 2.0 | Low = deterministic/factual; High = creative/diverse |
| Top-K | Restricts sampling to top K most likely tokens | 1 – 100 | Lower K = safer, less diverse output |
| Top-P (nucleus) | Restricts sampling to smallest token set whose cumulative probability ≥ P | 0.1 – 1.0 | Lower P = focused; higher P = more variety |
| Repetition Penalty | Penalizes tokens already generated | 1.0 – 1.5 (typical) | Reduces repetitive loops/phrases |

**Rule of thumb:** low temperature (0–0.3) for factual or coding tasks, higher temperature (0.7–1.0) for creative writing or brainstorming. Get this backwards and you'll either get a coding assistant that hallucinates syntax or a creative writer that reads like a legal disclaimer.

---
**Next:** [2.2 Prompt Engineering →](02-prompt-engineering.md)
