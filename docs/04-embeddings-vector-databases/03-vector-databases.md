# 4.3 Vector Databases

## 4.3.1 Purpose and functionality

- Store embedding vectors alongside metadata and enable fast Approximate Nearest Neighbor (ANN) search at scale
- Support filtering (metadata + vector hybrid search), namespacing/multi-tenancy, and CRUD operations on vectors
- Use indexing algorithms such as HNSW, IVF, or ScaNN under the hood for sub-linear search speed — this is what makes searching millions of vectors fast instead of scanning every one

## 4.3.2 Popular vector databases (pick one)

| Vector DB | Type | Best For |
|---|---|---|
| Chroma | Open-source, embedded/local | Prototyping, small-to-medium apps |
| Pinecone | Managed cloud | Production-scale, zero-ops |
| Weaviate | Open-source / managed | Hybrid search, GraphQL API |
| FAISS | Open-source library (Meta) | High-performance local/offline similarity search |
| LanceDB | Open-source, embedded | Serverless, multimodal, disk-based efficiency |
| Qdrant | Open-source / managed | High performance, rich filtering |
| Supabase (pgvector) | Postgres extension | Teams already on Postgres/Supabase |
| MongoDB Atlas | Managed, vector search add-on | Teams already on MongoDB |

**Quick decision guide:**
- Just prototyping → **Chroma**
- Going to production, don't want to manage infra → **Pinecone**
- Already on Postgres or MongoDB → use the vector extension on what you have (**pgvector** or **MongoDB Atlas**) instead of adding a new system
- Need heavy filtering alongside vector search → **Qdrant** or **Weaviate**

## 4.3.3 Implementing vector search

**Step 1 — Indexing embeddings**
- Convert documents into embeddings and insert them into the vector DB's index along with metadata (source, chunk ID, permissions)

**Step 2 — Performing similarity search**
- Embed the incoming query with the SAME embedding model used for indexing
- Run an ANN search, optionally with metadata filters, to fetch the top-K matches

> **Reminder:** always use the same embedding model for indexing and querying — mixing models produces meaningless similarity scores. This is worth repeating because it's the single most common source of "my RAG results are garbage" bug reports.

---
**Next:** [5. RAG (Retrieval-Augmented Generation) →](../05-rag/)
