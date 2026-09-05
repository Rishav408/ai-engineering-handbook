# 4.2 Embedding Models

## Proprietary

| Model / Provider | Notes |
|---|---|
| OpenAI Embeddings API (text-embedding-3) | High quality, simple API, widely used default |
| Gemini Embedding | Strong multilingual + multimodal support |
| Cohere Embed | Optimized for enterprise RAG & search |

## Open source

| Model / Provider | Notes |
|---|---|
| Sentence Transformers | Popular Python library; many pretrained embedding models |
| Models on Hugging Face | Community embedding models (e.g., BGE, E5, GTE families) |
| Jina Embeddings | Long-context, multilingual, competitive open embeddings |

## How to pick

- **Default, no strong constraints** → OpenAI text-embedding-3 — good quality, minimal setup
- **Multilingual or multimodal requirements** → Gemini Embedding
- **Enterprise RAG at scale, need retrieval-tuned performance** → Cohere Embed
- **Self-hosting, cost-sensitive, or need full control** → Sentence Transformers or a Hugging Face model (BGE/E5/GTE)
- **Long documents, non-English content** → Jina Embeddings

## One rule that matters more than the model choice

Always use the **same embedding model** for indexing and querying. Mixing models (e.g., embedding your documents with one model, then embedding search queries with a different one) produces meaningless similarity scores — the vectors live in different, incompatible spaces even if both models are "good." This is one of the most common and hardest-to-debug RAG mistakes, because nothing errors out, it just quietly returns bad results.

---
**Next:** [4.3 Vector Databases →](03-vector-databases.md)
