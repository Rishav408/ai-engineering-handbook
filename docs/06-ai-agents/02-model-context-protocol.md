# 6.2 Model Context Protocol (MCP)

## Definition

An open standard, introduced by Anthropic, that lets AI applications connect to external data sources and tools through a common protocol. Often described as **"the USB-C for AI apps"** — one standard connector instead of a custom integration for every tool/data source pairing.

## Core components

| Component | Role |
|---|---|
| **MCP Host** | The AI application (e.g., an IDE, chat client) that wants to access external context/tools |
| **MCP Client** | Lives inside the host; manages a 1:1 connection to an MCP server |
| **MCP Server** | Exposes specific tools, resources, or data to clients over the protocol |
| **Data Layer** | Defines the JSON-RPC based messages/schema exchanged between client and server |
| **Transport Layer** | The channel used — local (stdio) or remote (HTTP/SSE) |

## How it fits into the bigger picture

MCP is the standardized plumbing referenced back in [2.3 Context Engineering](../02-working-with-llms/03-context-engineering.md) — it's one way (increasingly the default way) that external context sources get connected to a model without every application reinventing its own integration layer.

## Developing with MCP

**Building an MCP Server**
- Define and expose tools/resources (functions, data endpoints) that any MCP-compatible client can discover and call

**Building an MCP Client**
- Implement the connector logic inside a host application to discover and invoke a server's tools

**Connecting to a local server**
- Use **stdio transport** to run/connect to an MCP server on the same machine — e.g., a local filesystem tool

**Connecting to a remote server**
- Use **HTTP/SSE transport** to connect to a hosted MCP server over the network — e.g., a SaaS integration

## When you'd actually reach for MCP

- Building a tool/data connector once and wanting it usable across multiple AI applications (Claude, IDEs, custom agents) without rewriting the integration each time
- Building an AI application (a host) and wanting to plug into an existing ecosystem of MCP servers instead of building every tool integration from scratch

---
**Next:** [7. AI Safety & Ethics →](../07-ai-safety-ethics/)
