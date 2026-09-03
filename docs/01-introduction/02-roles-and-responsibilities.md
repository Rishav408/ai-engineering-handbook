# 1.2 Roles and Responsibilities

An AI Engineer's day-to-day work breaks down into a handful of recurring responsibilities. None of these require training a model from scratch — all of them require solid software engineering plus a working knowledge of how LLMs behave.

## Core responsibilities

**Design and ship LLM-powered features**
- Chatbots, copilots, RAG-based search, agents that complete tasks on a user's behalf
- This is the visible, product-facing part of the job

**Choose the right model for the job**
- Not every task needs the biggest or most expensive model
- Pick between closed models (GPT, Claude, Gemini) and open-source ones (Llama, Mistral) based on cost, latency, and required output quality
- A support chatbot and a legal document summarizer have very different requirements, even though both are "just calling an LLM"

**Build retrieval pipelines**
- Most real products need the model to answer using information it wasn't trained on: internal docs, a knowledge base, live data
- Flow: chunk documents → embed them → store in a vector database → retrieve the right pieces at query time → re-rank results before they reach the model

**Engineer prompts and context windows**
- Not just "writing a good prompt" — deciding what goes into the model's context on every call
- System instructions, retrieved documents, conversation history, tool outputs — all competing for a limited token budget without blowing past cost or latency targets

**Build and orchestrate agents**
- Increasingly, the job isn't just getting the model to answer a question — it's getting the model to take multi-step action
- Loop: call a tool → check the result → decide what to do next → call another tool
- Making that loop reliable, and stopping it from spiraling or looping forever, is its own skill

**Set up evaluation and monitoring**
- Once something ships, you need a way to know if it's actually working
- Build evaluation pipelines, log what the model actually said in production, watch for drift or degradation
- Put guardrails in place before a bad output reaches a user

**Work across teams**
- Sit between product/design (what should the AI-powered experience feel like) and data teams (who own the grounding data)
- Translate between "what would make this feel magical to the user" and "here's what's actually feasible given the model's limits"

## The common thread

Every responsibility above is about wrapping a pre-built model in enough engineering that it becomes a dependable product feature, not just a demo.

---
**Next:** [1.3 Impact on Product Development →](03-impact-on-product-development.md)