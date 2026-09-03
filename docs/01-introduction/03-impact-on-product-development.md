# 1.3 Impact on Product Development

Bringing LLMs into a product doesn't just add a feature — it changes how the product gets built, tested, and priced. Four shifts matter most.

## 1. From deterministic to probabilistic behavior

- Traditional software: same input, same output, every time
- LLM-powered features: ask the same question twice, get two differently-worded (or differently-structured) answers
- This breaks the usual QA playbook — you can't write a unit test checking for an exact string match anymore
- Testing an AI feature means testing for a *range* of acceptable behavior, not a single correct answer

## 2. Faster prototyping, same or slower path to reliability

- Calling an existing foundation model instead of training one means going from idea to working prototype in days, not months
- That's real, and it's part of why AI features have exploded in the last few years
- But "fast to prototype" ≠ "fast to make reliable"
- The gap between a demo that works 80% of the time and a production feature that works consistently is where most of the actual engineering time goes

## 3. New cost dimensions that directly affect UX

| Dimension | What it determines |
|---|---|
| Token usage | Per-request cost |
| Inference latency | How snappy the feature feels |
| Rate limits | How many users you can serve concurrently before queuing/failing |

- None of this is optional to think about
- A feature that's technically correct but takes eight seconds to respond, or costs more per request than the product's margin allows, isn't shippable — no matter how good the output is

## 4. New categories of risk

- **Hallucination** — the model states something confidently that's wrong or made up
- **Prompt injection** — a malicious input manipulates the model into ignoring its instructions
- **Data leakage** — sensitive information from context or training ends up somewhere it shouldn't

These aren't edge cases you patch after launch. Design for them from day one, the same way you'd design for SQL injection or auth bypass in traditional software — by the time a hallucinated answer or a leaked document reaches a user, the damage is already done.

## What this means in practice

Budget time for evaluation and guardrails the same way you'd budget time for security review — not as an afterthought once the demo looks good. The demo working is the easy 20%. The other 80% is making it reliable, safe, and affordable at scale.

---
**Next:** [1.4 AI Engineer vs ML Engineer →](04-ai-engineer-vs-ml-engineer.md)