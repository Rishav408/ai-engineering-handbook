# 1.4 AI Engineer vs ML Engineer

These two roles get confused constantly — partly because both have "AI" or "ML" in the title, both work with models. The actual split comes down to one question: **are you building the model, or building on top of one that already exists?**

## Side-by-side comparison

| Aspect | AI Engineer | ML Engineer |
|---|---|---|
| Primary focus | Using pre-trained/foundation models via APIs | Building and training models from data |
| Core skills | Prompting, RAG, agents, orchestration | Statistics, model architecture, training loops |
| Typical stack | LangChain, LlamaIndex, vector DBs, LLM APIs | PyTorch/TensorFlow, MLOps, feature stores |
| Output | AI-powered product features | Trained or fine-tuned models |
| Data need | Small (for RAG/context) to none | Large labeled datasets |
| Time to ship | Days to weeks | Weeks to months |

## Why the split exists

- Before foundation models got good enough to use off the shelf, an AI feature meant training one from scratch
- That's still exactly what ML Engineers do, and it's still necessary for a lot of problems: fraud detection, recommendation systems, anything with proprietary structured data at scale
- What changed: models like GPT-4, Claude, and Gemini are now good enough at general reasoning, writing, and code that most product ideas don't need a custom-trained model anymore
- They need someone who can take an existing model and wire it into a product reliably — that's the AI Engineer role, and it barely existed as a distinct title before roughly 2023

## Where the lines blur

- Plenty of people do both in practice
- An ML Engineer might fine-tune an open-source model *and* build the RAG pipeline that serves it
- An AI Engineer might need to understand embedding model internals well enough to pick the right one, without training it themselves
- The table above describes the center of each role, not a hard boundary

## Which one should you specialize in?

- Drawn to data pipelines, model architecture, the math behind why a model works → **ML Engineer**
- Drawn to building products, wiring systems together, getting a model to behave reliably inside a real application → **AI Engineer**

This repository is written for the second path.

---
**Next:** [1.5 Common Terminology (Glossary) →](05-glossary.md)