# 0. Prerequisites

Before starting the AI Engineer track, you should have a foundation in standard software engineering. AI Engineering is built **on top of** programming fundamentals — it is not a substitute for them.

## Required foundation

Pick **any ONE** of the following tracks as your starting foundation, depending on which side of the stack you want to build AI-powered products on:

| Track | Focus | Best if you want to... |
|---|---|---|
| **Frontend** | HTML/CSS/JS, frameworks (React, Vue), state management, UI/UX basics | Build AI-powered user interfaces, chat UIs, copilots |
| **Backend** | Server-side languages, APIs, databases, authentication, system design | Build AI orchestration layers, RAG pipelines, agent backends |
| **Full-Stack** | Both of the above, end-to-end | Ship complete AI products solo, from UI to inference layer |

> **Note:** AI Engineering builds on top of standard software engineering skills; it is **NOT** a substitute for programming fundamentals. If you skip this step, you'll be able to follow tutorials but will struggle to debug, scale, or productionize anything you build.

## Why this matters

Most of what makes an AI Engineer effective isn't the AI part — it's the engineering part:

- **APIs and SDKs**: Every LLM provider (OpenAI, Anthropic, Gemini) is consumed through a standard REST API or SDK. If you're not comfortable making HTTP requests, handling async code, and parsing JSON, the "AI" layer becomes a black box you can't debug.
- **Data handling**: RAG pipelines, embeddings, and evaluation all require comfort with data structures, file I/O, and basic data transformation — skills from general backend/software engineering, not AI-specific training.
- **Production concerns**: Rate limits, error handling, caching, logging, and deployment are the same concerns as any other software system — AI just adds new failure modes (hallucination, prompt injection) on top of the usual ones.
- **Version control & collaboration**: Git, code review, and CI/CD are assumed baseline skills for any engineering role, AI-focused or not.

## Recommended path if you're starting from zero

1. Pick a track (Frontend, Backend, or Full-Stack) based on the roadmap.sh guides linked above.
2. Get comfortable with at least one programming language end-to-end (Python is the de facto standard for AI Engineering — see [resources/python.md](../../resources/python.md)).
3. Build 1–2 small non-AI projects first (a CRUD app, a simple API) to internalize the fundamentals.
4. Then move on to [1. Introduction](../01-introduction/) to start the AI Engineer track proper.

## Further Reading

- [Frontend Development Roadmap](https://roadmap.sh/frontend)
- [Backend Development Roadmap](https://roadmap.sh/backend)
- [Full-Stack Development Roadmap](https://roadmap.sh/full-stack)
- [AI Python for Beginners – Deeplearning.ai](https://www.deeplearning.ai/short-courses/ai-python-for-beginners/)

---
**Next:** [1. Introduction →](../01-introduction/)
