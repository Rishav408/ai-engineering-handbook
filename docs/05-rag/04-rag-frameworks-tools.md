# 5.4 RAG Frameworks & Tools

Once you understand the [five-stage pipeline](03-implementing-rag-pipeline.md), you have a choice: wire it together yourself, or use a framework that handles most of the plumbing.

## Ways of implementing RAG

| Approach | Description |
|---|---|
| Using SDKs directly | Manually wire embedding API + vector DB + LLM API — maximum control, more code to maintain |
| LangChain | Popular orchestration framework with pre-built RAG chains/retrievers |
| LlamaIndex | Framework specialized for data ingestion/indexing + retrieval pipelines |
| Haystack | Production-grade NLP/RAG framework (deepset) with pipelines & components |
| RAGFlow | Open-source RAG engine focused on deep document understanding |

## How to choose

- **Learning how RAG actually works, or need very custom logic** → build with SDKs directly. You'll understand every failure mode because you wrote every step.
- **Building general LLM applications where RAG is one piece of a larger chain** → LangChain. Its retriever abstractions integrate cleanly with the rest of a LangChain-based app.
- **RAG is the primary thing you're building, especially with complex data ingestion needs** → LlamaIndex. It's purpose-built for indexing and retrieval, not general orchestration.
- **Production deployment with a need for modular, swappable pipeline components** → Haystack.
- **Heavy documents (PDFs, scanned files, complex layouts) where understanding document structure matters** → RAGFlow.

## A practical note

Most teams overthink this choice early on. Starting with SDKs directly for a prototype (even a rough one) teaches you where your specific bottleneck actually is: chunking quality, retrieval relevance, or generation grounding. Once you know which stage is the problem, picking a framework that specializes in fixing that stage becomes a much easier decision than picking one upfront based on GitHub stars.

---
**Next:** [6. AI Agents →](../06-ai-agents/)
