# 2.3 Context Engineering

## Context engineering vs prompt engineering

- **Prompt engineering** = crafting the instruction
- **Context engineering** = designing the full pipeline that decides *what data enters the context window* in the first place: retrieval, memory, tool outputs, history

A perfectly written prompt still fails if the context feeding it is wrong, missing, or stale. This is the discipline that most teams underinvest in relative to prompt tweaking.

## What is a context layer?

An abstraction layer that assembles, filters, and formats all context sources before they reach the model. It sits between your application and the LLM call — the model never sees your raw database or document store, it sees whatever this layer decides to hand it.

## Context sources

- Conversation history
- RAG-retrieved documents
- Tool/API outputs
- User profile or memory
- System state
- External knowledge bases

## Where MCP fits in

**Model Context Protocol (MCP)** is a standardized protocol for connecting LLMs to external context and tool sources. Covered in depth under [6.1 Building AI Agents](../06-ai-agents/01-building-ai-agents.md) — for context engineering purposes, just know it's the standardized plumbing for getting external data into the model's hands.

## Two concerns that come with every context layer

**Context security**
- Preventing sensitive data from leaking into prompts
- Preventing untrusted retrieved content from injecting malicious instructions (prompt injection via retrieved data, not just user input)

**Context evaluation**
- Measuring whether the assembled context is relevant, sufficient, and free of noise or conflicting information before generation even happens

## Context engineering techniques

**RAG & dynamic filters**
- Retrieve only the most relevant chunks at query time
- Apply metadata filters (date, source, permissions) to narrow results before they reach the model

**Memory systems**
- Short-term (session) memory vs long-term (persistent, cross-session) memory
- Often implemented via summarization + vector store

**Context compaction**
- Summarize or prune older conversation turns to stay within the context window without losing critical information

**Long-context processing**
- Strategies for handling very large inputs (100K+ tokens): chunk-and-map-reduce, hierarchical summarization, sliding windows

**State & historical context**
- Tracking application/task state, not just chat text, so multi-turn or multi-agent workflows stay consistent

**Multi-agent context sharing**
- Passing relevant (not all) context between cooperating agents to avoid context bloat and cross-contamination

**Context isolation**
- Keeping unrelated tasks/sessions in separate context scopes to prevent instruction bleed and privacy leaks

## Context failure modes

| Failure mode | What happens |
|---|---|
| **Context poisoning** | Bad data enters context and compounds over subsequent turns |
| **Context distraction** | Too much irrelevant info drowns out what actually matters |
| **Context clash** | Conflicting sources in the same context confuse the model |
| **Context rot** | Stale info sits in context past its useful life and gets treated as current |

## Tools & context warehouses

| Tool | Category | Purpose |
|---|---|---|
| **Atlan** | Data/Context Catalog | Metadata management and data discovery for grounding context |
| **DataHub** | Data/Context Catalog | Open-source metadata platform for lineage and discovery |
| **modus** | Context Warehouse | Agentic context/data layer tooling |
| **PostHog** | Product Analytics | Behavioral/event data usable as context signals for personalization |

---
**Next:** [3. AI Models →](../03-ai-models/)
