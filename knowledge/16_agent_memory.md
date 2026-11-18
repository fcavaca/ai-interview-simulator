# The four types of AI agent memory (IBM Technology)
Source: https://www.youtube.com/watch?v=BacJ6sEhqMo

## Key points
- Human analogy: short-term memory, factual knowledge, learned skills, personal experience.
- The **CoALA** framework (*Cognitive Architectures for Language Agents*, Princeton) defines four agent memory types:
  1. **Working memory**: the **context window** (current conversation, system instructions, loaded files). Like **RAM**: fast but **volatile** (gone when the session ends) and **limited** (even 1M+ tokens has a ceiling, and performance degrades on information "lost in the middle"). Every chatbot has this.
  2. **Semantic memory**: the knowledge base of facts, rules, conventions and documentation. In theory vector databases or knowledge graphs; in practice often simple **markdown files**, e.g. **CLAUDE.md** in a project root (architecture, conventions, build commands, what not to do), loaded at the start of every session. Without it the agent repeats the same mistakes.
  3. **Procedural memory**: how to do things, via **agent skills (SKILL.md)**, loaded by **progressive disclosure**: an index of names and descriptions (~100 tokens per skill), then full instructions when a task matches, then extra files only when needed. Unlike semantic memory, it isn't always in context.
  4. **Episodic memory**: a record of past interactions and decisions. Saving every transcript is naive. Production systems **distil** what's worth remembering ("last time the auth bug was in the middleware layer"), and this starts to look like learning. It is the **hardest** type: what to delete, when information becomes obsolete. **Forgetting is an engineering problem.**
- Not every agent needs all four:
  - **simple reflex agent** (thermostat, routing bot): working memory only
  - **narrow support agent** (password reset): working + procedural
  - **coding agent**: all four
- **Memory is what separates a chatbot from an agent**: an agent's responses are shaped by persistent knowledge and accumulated experience.

## Things an interviewer can ask
- Name and define the four memory types, with an example implementation of each.
- Why is working memory like RAM?
- Why is episodic memory the hardest to get right?
- Which memory types does a simple password-reset bot need?
