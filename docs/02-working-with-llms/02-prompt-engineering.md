# 2.2 Prompt Engineering

Prompt engineering is the practice of crafting inputs — instructions, examples, structure — to reliably get the output you want from a model. It sits one level below [context engineering](03-context-engineering.md): prompt engineering crafts the instruction, context engineering decides what data the instruction gets to work with.

## Prompt anatomy

Every well-built prompt is made of some combination of these components:

| Component | What it is |
|---|---|
| **Input Format** | Structure of the prompt itself — plain text, XML-tagged sections, Markdown, or JSON schema for structured tasks |
| **System Prompting** | A persistent instruction layer, separate from user turns, defining the model's role, tone, and hard rules for the entire session |
| **Role & Behavior** | Explicitly assigning a persona ("You are a senior backend engineer...") to steer style, depth, and vocabulary |
| **Context** | Background information, documents, or data the model needs to answer accurately — distinct from conversation history |
| **Constraints** | Explicit boundaries: length limits, forbidden topics, output language, formatting rules |
| **Structured Output** | Forcing responses into JSON/XML/schema format for reliable machine parsing, via schema constraints or function-calling |

Miss the system prompt and you get inconsistent behavior across turns. Miss constraints and you get outputs that technically answer the question but ignore your format. Most "the model isn't listening to me" complaints trace back to one of these six components being missing or vague.

## Prompting techniques

| Technique | How it works | Best for |
|---|---|---|
| **Zero-Shot** | Ask the model directly, no examples | Simple, well-known tasks |
| **Few-Shot** | Provide 2–5 input/output examples in the prompt | Tasks needing a specific format or style |
| **Chain-of-Thought (CoT)** | Ask the model to reason step-by-step before answering | Math, logic, multi-step reasoning |
| **ReAct** | Interleave Reasoning + Acting (tool calls) in a loop | Agentic tasks needing tools or search |

Start with zero-shot. If the output format or tone is off, move to few-shot before reaching for anything more complex — it fixes more problems than people expect.

## Model interaction mechanics

**Function calling**
- The model outputs a structured call (name + arguments) matching a developer-defined schema
- Your application executes it and feeds the result back to the model
- This is the mechanism underneath every tool-using agent

**Prompt caching**
- Reuses the KV-cache for repeated prompt prefixes, e.g. long system prompts, across calls
- Cuts latency and cost significantly when the same large context (like a system prompt or a document) gets reused across many requests

**Streaming responses**
- Tokens return incrementally over a connection (SSE/WebSocket) instead of waiting for the full completion
- Critical for perceived UX speed — a response that streams in over 3 seconds feels faster than one that appears all at once after 3 seconds, even though the total time is identical

> For a deeper dive specifically on prompting, see the [Prompt Engineering Roadmap on roadmap.sh](https://roadmap.sh/prompt-engineering).

---
**Next:** [2.3 Context Engineering →](03-context-engineering.md)
