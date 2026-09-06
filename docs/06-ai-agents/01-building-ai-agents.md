# 6.1 Building AI Agents

## Definition

An **AI Agent** = an LLM given the ability to reason, plan, use tools, and act iteratively toward a goal — instead of producing a single one-shot response. The distinction from a plain chatbot is the loop: an agent keeps working across multiple steps until the goal is met, not just until it's answered once.

## Use cases

- Autonomous coding assistants
- Research agents
- Customer-support resolution agents
- Data-pipeline agents
- Computer-use agents

## Core pattern: ReAct prompting

The core agent loop:

**Reason** (think) → **Act** (call a tool) → **Observe** (read result) → repeat until goal is met

This loop is the mechanism underneath almost every agent framework, regardless of what it's called in that framework's docs.

## Core mechanism: tools & function calling

- Agents are given a defined set of callable tools — APIs, code execution, search
- The model decides which tool to call and with what arguments, based on the current reasoning step
- This is the same function-calling mechanism covered in [2.2 Prompt Engineering](../02-working-with-llms/02-prompt-engineering.md) — agents are what you get when you wrap that mechanism in a loop instead of calling it once

## Pattern: multi-agent systems

- Multiple specialized agents (planner, coder, reviewer, etc.) collaborate
- Often coordinated by an orchestrator/supervisor agent that assigns sub-tasks and merges results
- Used when a single agent's context or specialization can't reasonably cover the full task — e.g., a "coder" agent shouldn't also be the one deciding if its own code is correct

## Frameworks & platforms for building agents

| Approach | Description |
|---|---|
| Manual Implementation | Hand-roll the ReAct loop and tool dispatch yourself — full control, most effort |
| OpenAI AgentKit & Agent SDK | OpenAI's official framework for building/orchestrating agents with built-in tools |
| Claude Agent SDK | Anthropic's SDK for building agents on Claude with native tool-use & computer-use support |
| Vertex AI Agent Builder | Google Cloud's managed platform for building enterprise agents |
| Google ADK | Agent Development Kit — Google's open framework for building/deploying agents |

**How to choose:** manual implementation if you're learning the mechanics or need very custom control flow; a provider SDK (OpenAI, Claude, Google) if you're already committed to that model provider and want built-in tool-use handling; a managed platform (Vertex AI Agent Builder) if you need enterprise deployment without building the orchestration layer yourself.

> See the dedicated [AI Agents Roadmap on roadmap.sh](https://roadmap.sh/ai-agents) for a deeper dive into this sub-track.

---
**Next:** [6.2 Model Context Protocol (MCP) →](02-model-context-protocol.md)
