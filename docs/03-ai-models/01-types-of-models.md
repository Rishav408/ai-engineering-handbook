# 3.1 Types of Models

## Pre-trained models

Foundation models already trained on massive general-purpose corpora, ready to use via API or download. This is the default starting point for almost all AI engineering work — you're not training anything, you're consuming what already exists.

## Closed vs open source

- **Closed** — weights hidden, accessed only via paid API (GPT, Claude, Gemini)
- **Open source** — weights downloadable and self-hostable (Llama, Qwen, DeepSeek, Gemma)
- **Self-hosted** — open-source models deployed on owned/rented infrastructure, chosen for data privacy, cost control at scale, or offline/edge use cases

## Closed vs open source — quick comparison

| Factor | Closed Source | Open Source / Self-Hosted |
|---|---|---|
| Setup effort | Minimal — just an API key | High — infra, GPUs, ops |
| Cost model | Pay-per-token | Upfront/infra cost, cheaper at scale |
| Data privacy | Data sent to vendor | Full control, on-prem possible |
| Customization | Limited (prompting only, some fine-tuning) | Full (fine-tune, quantize, modify) |
| Quality (frontier tasks) | Generally highest (SOTA) | Rapidly closing the gap |

## Which one should you default to?

- Building a prototype or an MVP where speed matters more than cost control → **closed**
- Handling sensitive data that can't leave your infrastructure, or serving at a scale where per-token pricing gets expensive → **open source, self-hosted**
- Most teams start closed and only move to self-hosting once cost or compliance actually forces the question — don't self-host preemptively

---
**Next:** [3.2 Choosing the Right Model →](02-choosing-the-right-model.md)
