# 3.2 Choosing the Right Model

## 3.2.1 Closed models

| Provider | Model Family | Known Strength |
|---|---|---|
| Anthropic | Claude (Sonnet, Opus, Haiku) | Coding, agentic tool-use, long-context reasoning, safety |
| Google | Gemini | Native multimodality, huge context windows, ecosystem (Workspace) |
| OpenAI | GPT-series, o-series (reasoning) | General-purpose strength, o-series for deep reasoning |
| Cohere | Command series | Enterprise RAG, retrieval, multilingual |
| Mistral | Mistral/Magistral | Efficient, strong open+closed hybrid lineup, EU-based |

## 3.2.2 Open source models

| Model Family | Maintainer | Notes |
|---|---|---|
| Llama | Meta | Widely adopted general-purpose open-weight family |
| DeepSeek | DeepSeek AI | Strong reasoning/coding performance at low cost, MoE architecture |
| Qwen | Alibaba | Strong multilingual + coding, wide size range |
| Gemma | Google | Lightweight, efficient, good for edge/local deployment |

## 3.2.3 Platforms & ecosystem

- **Hugging Face Hub** — central repository for open-source models, datasets, and demo Spaces; the default discovery hub
- **Hugging Face Tasks** — task-based taxonomy (text-generation, embeddings, classification, etc.) to filter and benchmark models by use case
- **Transformers.js** — run Hugging Face models directly in the browser/Node via WebAssembly/WebGPU, no server round-trip
- **Ollama** — simplest way to run open-source LLMs locally with a single CLI command; ships a local REST API
- **LM Studio** — GUI desktop app for discovering, downloading, and chatting with local models, beginner friendly
- **OpenRouter** — unified API gateway that routes requests to 100+ models (open & closed) through one endpoint/key, useful for comparison and fallback routing

## 3.2.4 APIs & SDKs

| API / SDK | Provider | Notes |
|---|---|---|
| OpenAI Response API | OpenAI | Unified API for text, tools, structured outputs, reasoning |
| Claude Messages API | Anthropic | Core API for Claude models; supports tool use, streaming, vision |
| Google Gemini API | Google | Access to Gemini family; native multimodal input |
| Hugging Face Inference SDK | Hugging Face | Programmatic access to hosted/self-hosted HF models |
| OpenAI-compatible APIs | Various (Ollama, vLLM, OpenRouter, etc.) | Many providers mimic OpenAI's schema for drop-in compatibility |

## How to actually pick

Don't start from "which model is best" — start from what you're optimizing for:

- **Coding/agentic tool-use** → Claude (Sonnet/Opus)
- **Huge context or native multimodal input** → Gemini
- **General-purpose or deep reasoning tasks** → GPT-series / o-series
- **Enterprise RAG, multilingual retrieval** → Cohere Command
- **Cost-sensitive, self-hosted, strong reasoning** → DeepSeek or Qwen
- **Edge/local deployment** → Gemma

If you're not sure yet, prototype against 2–3 candidates through **OpenRouter** before committing — it lets you swap models with a config change instead of rewriting your integration layer.

---
**Next:** [4. Embeddings & Vector Databases →](../04-embeddings-vector-databases/)
