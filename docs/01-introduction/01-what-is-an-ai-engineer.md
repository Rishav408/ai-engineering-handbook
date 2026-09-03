# 1.1 What is an AI Engineer?

## Definition

An **AI Engineer** is a software engineer who specializes in building applications powered by AI models — mainly Large Language Models (LLMs) — rather than training models from scratch. The role focuses on **integration, orchestration, and productization** of foundation models (via APIs/SDKs) into real-world products, not on the model training or research pipeline itself.

## Core competencies

An AI Engineer is expected to be comfortable across the following areas:

- **Prompt engineering** — designing instructions that reliably elicit the desired model behavior
- **Context engineering** — managing what information (system prompts, retrieved data, history) is visible to the model at inference time
- **RAG pipelines** — retrieval-augmented generation: chunking, embedding, storing, and retrieving external knowledge for the model to use
- **Agentic workflows** — orchestrating multi-step reasoning and tool-calling so a model can take actions, not just generate text
- **Vector databases** — storing and querying embeddings for semantic search and retrieval
- **Evaluation** — measuring whether an AI system is actually working (accuracy, relevance, safety) before and after shipping
- **Safety** — guarding against hallucination, prompt injection, and data leakage in production systems

## AI Engineer vs. ML Engineer — the key distinction

This is the most common point of confusion for people entering the field, so it's worth being precise:

| | AI Engineer | ML Engineer |
|---|---|---|
| **Primary focus** | Integration & orchestration of pre-trained foundation models | Training, fine-tuning, and the full ML pipeline |
| **Typical workflow** | API calls → prompt design → RAG/agent orchestration → evaluation | Data collection → feature engineering → model training → deployment |
| **Core skill set** | Software engineering, API integration, prompt/context design | Statistics, model architecture, training infrastructure |
| **Builds models?** | Rarely — consumes existing foundation models (GPT, Claude, Gemini, Llama) | Yes — designs, trains, and fine-tunes models |
| **Time to prototype** | Days (no training required for most use cases) | Weeks to months (data prep + training cycles) |
| **Primary tools** | LangChain, LlamaIndex, vector DBs, provider SDKs | PyTorch, TensorFlow, training clusters, MLOps pipelines |

In short: an **ML Engineer builds the engine**; an **AI Engineer builds the car around it** — the product experience, the guardrails, the integration into a real workflow.

## Why the distinction matters in practice

Before the rise of capable foundation models (GPT-3/4, Claude, Gemini), building an AI feature almost always meant training or fine-tuning a model — squarely ML Engineer territory. The emergence of strong general-purpose foundation models, accessible via API, created a new role: someone who can take those models and turn them into reliable, safe, production-grade products **without** needing to train anything from scratch. That's the AI Engineer role, and it's why the discipline has its own distinct skill tree (this repo) separate from classical ML Engineering.

## Further Reading

- [Agents – Chip Huyen](https://huyenchip.com/2025/01/07/agents.html)
- [AI Engineering (O'Reilly)](https://www.oreilly.com/library/view/ai-engineering/9781098166298/)
- [Designing Machine Learning Systems](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/)

---
**Next:** [1.2 Roles and Responsibilities →](02-roles-and-responsibilities.md)
