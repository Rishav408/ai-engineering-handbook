# 5.1 What are RAGs?

## Definition

RAG (Retrieval-Augmented Generation) is an architecture pattern that grounds LLM responses in external, up-to-date, or proprietary data retrieved at query time. It reduces hallucination and removes the need to retrain the model every time your underlying knowledge changes.

The core idea: instead of relying only on what the model memorized during training, you fetch relevant information right before generation and hand it to the model as context.

## Use cases

- **Enterprise knowledge-base / internal documentation Q&A** — employees ask questions, answers pull from internal wikis/docs instead of a stale FAQ
- **Customer support chatbots** grounded in product docs — answers stay accurate as the product changes, without retraining anything
- **Legal/medical document search and summarization** — retrieval surfaces the exact clause or study, generation explains it in plain language
- **Code assistants grounded in a private codebase** — the model can reference your actual internal libraries and conventions, not just public training data

## Why RAG exists

Two problems it solves that prompting alone can't:

1. **Knowledge cutoff** — the model was trained on data up to some date; RAG lets it answer questions about anything more recent, without retraining
2. **Private/proprietary data** — the model never saw your internal docs during training; RAG is how you make it "aware" of them at query time, without ever putting that data into a training run

For how RAG compares to the other way of updating model knowledge, see [5.2 RAG vs Fine-tuning](02-rag-vs-fine-tuning.md).

---
**Next:** [5.2 RAG vs Fine-tuning →](02-rag-vs-fine-tuning.md)
