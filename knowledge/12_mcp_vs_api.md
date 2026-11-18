# MCP vs API (IBM Technology)
Source: https://www.youtube.com/watch?v=7j1t3UZA1TY

## Key points
- **MCP (Model Context Protocol)** is an open standard introduced by **Anthropic in late 2024** that standardises how applications give LLMs context and tools. Analogy: a **USB-C port for AI apps**, one standard connector for any peripheral.
- Architecture:
  - The **MCP host** (the AI app) runs **MCP clients**.
  - Each client opens a **JSON-RPC 2.0** session to an **MCP server**.
  - Each server exposes capabilities, e.g. a database, a code repository or email.
- MCP serves agents' two needs: **contextual data** and **tool use**.
- Server **primitives**:
  1. **Tools**: actions the AI can call (get_weather, create_event); the server executes them.
  2. **Resources**: read-only data (files, database schemas).
  3. **Prompt templates**: suggested prompts.
- Every server publishes a machine-readable catalogue (tools/list, resources/list, prompts/list). This is **dynamic discovery**: agents learn at runtime what a server can do, and new features work without redeploying code.
- **API** (application programming interface): a set of rules for requesting another system's data or services. It is an **abstraction layer**, so the client doesn't need to know the server's internals. Example: a payment API in e-commerce.
  - **REST APIs** run over HTTP using GET (read), POST (create), PUT (update) and DELETE, e.g. GET /books/123 or POST /loans, and usually return JSON. Many LLMs are themselves offered over REST.
- **Similarities**: both are client-server, both are abstraction layers, and both simplify integration.
- **Differences**:
  - MCP is **purpose-built for LLM agents**; APIs are **general-purpose**.
  - MCP has **dynamic discovery**; REST clients must be updated by developers when an API changes.
  - MCP has a **standard interface**: five MCP servers answer the same calls ("build once, integrate many"), whereas five REST APIs may need five adapters.
- They are **layers, not rivals**: many MCP servers are **wrappers around existing APIs**. For example, the GitHub MCP server translates tool calls into GitHub REST requests.

## Things an interviewer can ask
- What problem does MCP solve? Explain the USB-C analogy.
- Name the three MCP primitives.
- Give two differences between MCP and REST APIs, and explain how they work together.
