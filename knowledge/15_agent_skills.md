# Agent skills (IBM Technology)
Source: https://www.youtube.com/watch?v=Lg-meK5IU8Q

## Key points
- LLMs know lots of **facts** but lack **procedural knowledge**: how work is actually done in *your* organisation, e.g. a 47-step workflow for a compliant financial report. Without it, someone must prompt every step each time, or the agent guesses.
- A **skill** is a folder containing a **SKILL.md** markdown file:
  - **YAML front matter** with two **mandatory fields**:
    - **name**
    - **description**: what the skill does and **when to use it**. This is the *trigger condition*, so it must be well written.
    - Optional fields: author, version.
  - The **body**: plain-markdown instructions, step-by-step workflows, rules, input/output examples.
  - **Optional folders**: `scripts/` (executable Python, JS or bash), `references/` (extra docs loaded if needed), `assets/` (templates, data files).
- **Progressive disclosure** keeps hundreds of skills from flooding the context window. It has three tiers:
  1. **Metadata only**: at startup, just the name and description of each skill, a few tokens each, like a table of contents.
  2. **Full instructions**: when a request matches a description (judged by the LLM's own reasoning), the full SKILL.md body is loaded.
  3. **Resources**: scripts, references and assets are loaded only when a task needs them.
- How skills compare with other ways of giving an agent knowledge:
  - **MCP** gives *tool access* (what the agent can reach), but not when or how to use it.
  - **RAG** gives *factual reference* knowledge, but doesn't teach how to do something.
  - **Fine-tuning** bakes knowledge into the weights: permanent but expensive, and it must be redone when the model changes.
  - **Skills** give *procedural* knowledge: how, in what order, with what judgment. They are just files, so they can be version-controlled, easily updated and moved between platforms. Skills often *use* MCP: MCP provides the capability, and the skill provides the judgment.
- SKILL.md is an **open standard** (agentskills.io, Apache 2.0), adopted by Claude Code, OpenAI Codex and others, so a skill works on any platform that supports it.
- Cognitive-science mapping:
  - **semantic memory** (facts) ↔ RAG and knowledge bases
  - **episodic memory** (experiences) ↔ conversation logs
  - **procedural memory** (skills) ↔ skill files
- **Security**: skills can run scripts with access to files, environment variables and API keys. Audits of public skills found prompt injection, tool poisoning and hidden malware. Review a skill like any software dependency before installing it.

## Things an interviewer can ask
- What are the two mandatory fields of a SKILL.md, and why does the description matter so much?
- Explain progressive disclosure and its three tiers.
- Skills vs MCP vs RAG vs fine-tuning: what kind of knowledge does each provide?
- What is the security risk of skills?
