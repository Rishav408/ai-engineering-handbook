# 5.2 RAG vs Fine-tuning

These are the two main ways to get a model to "know" or "do" something it doesn't by default. They solve different problems and are often confused as competing options when they're usually complementary.

## Comparison

| Aspect | RAG | Fine-tuning |
|---|---|---|
| Purpose | Inject fresh/external knowledge | Change model behavior/style/skill |
| Data freshness | Always current (retrieved live) | Frozen at training time |
| Cost | Lower, no retraining needed | Higher — compute + data prep |
| Transparency | Source-citable, explainable | Opaque — knowledge baked into weights |
| Best for | Knowledge-intensive Q&A | Tone, format, domain-specific reasoning style |

## How to decide

Ask what's actually failing:

- **The model doesn't know something** (a fact, a document, current data) → **RAG**. Retrieval fixes knowledge gaps without touching the model itself.
- **The model knows the facts but responds in the wrong tone, format, or reasoning style** → **fine-tuning**. No amount of retrieved context fixes a model that consistently answers in the wrong register or skips your required output format.
- **Both problems at once** → use both. Fine-tune for behavior/style, RAG for facts. They're not mutually exclusive — a fine-tuned model can still retrieve context at query time.

## Why RAG is usually the first move

For most product use cases, the actual problem is "the model doesn't have my data," not "the model behaves wrong." RAG is cheaper, faster to iterate on, and doesn't require a training pipeline — so it's the default starting point. Reach for fine-tuning only once you've confirmed retrieval and prompting alone can't fix the behavior you're after.

---
**Next:** [5.3 Implementing the RAG Pipeline →](03-implementing-rag-pipeline.md)
