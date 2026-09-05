# 5.3 Implementing RAG — The Pipeline

Every RAG system, regardless of framework or vector DB choice, runs through the same five stages.

## The five stages

**Step 1 — Chunking**
- Split source documents into smaller passages: fixed-size, semantic, or recursive chunking
- Chunks need to fit context limits and match retrieval granularity — too large and you retrieve noise, too small and you lose surrounding meaning

**Step 2 — Embedding**
- Convert each chunk into a vector using an [embedding model](../04-embeddings-vector-databases/02-embedding-models.md)

**Step 3 — Vector database**
- Store the chunk embeddings plus metadata (source, chunk ID, permissions) for fast retrieval
- See [4.3 Vector Databases](../04-embeddings-vector-databases/03-vector-databases.md) for options

**Step 4 — Retrieval process**
- At query time, embed the user's query with the *same* embedding model used in Step 2
- Fetch the top-K most similar chunks, optionally with re-ranking to push the most relevant results to the top

**Step 5 — Generation**
- Inject the retrieved chunks into the prompt as context
- Let the LLM generate a grounded, cited answer using that context instead of relying purely on what it memorized during training

## Where pipelines usually break

- **Chunking too coarse or too fine** — get this wrong and no amount of downstream tuning fixes it, since bad chunks mean bad retrieval no matter how good the embedding model is
- **Mismatched embedding models** between indexing and querying (see the rule in [4.2 Embedding Models](../04-embeddings-vector-databases/02-embedding-models.md))
- **No re-ranking step** — raw top-K similarity search often surfaces marginally-relevant chunks alongside genuinely useful ones; re-ranking filters that noise before it reaches the model
- **Stale index** — documents change, but nobody re-embeds and re-indexes them, so retrieval quietly serves outdated information

---
**Next:** [5.4 RAG Frameworks & Tools →](04-rag-frameworks-tools.md)
