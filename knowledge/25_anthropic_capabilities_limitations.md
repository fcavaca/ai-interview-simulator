# AI Capabilities and Limitations (Anthropic Academy)
Source: https://www.coursera.org/learn/ai-capabilities-and-limitations (also at https://academy.claude.com/courses/ai-capabilities-and-limitations)

Companion to Anthropic's *AI Fluency* course. That course teaches the human skills (the 4Ds: **Delegation, Description, Discernment, Diligence**). This one teaches the **machine properties** those skills respond to. Goal: look at an unexpected AI output, recognise **which kind** of unexpected it is, and apply a **targeted fix instead of a generic retry**.

## Key points

### What "AI" means here
- Most AI in daily life is **not generative**: spam filters, recommendations and fraud detection classify or rank. This course is about **generative AI**: transformer-based models that produce new content **one token at a time**.
- The model is strong and weak along **four properties**: **Next Token Prediction, Knowledge, Working Memory, Steerability**.
- Each property is a **capability-to-limitation continuum**: the **same mechanism** produces both the strength and the weakness. **Calibrated trust** means locating your task on that continuum.

### How AI gets its character
- Politeness, helpfulness and caution are **trained in**, not natural.
- **Pre-training** produces a **document completer** that predicts what comes next, with no idea of "helping" anyone.
- **Fine-tuning** (using human judgments of good responses) adds assistant behaviour: treat input as a request, answer instead of rambling, decline harmful asks.
- That training leaves four **fingerprints**:
  - **Sycophancy**: a pull towards agreeing with the user's framing, even a wrong premise.
  - **Verbosity**: long answers by default.
  - **Over-caution**: occasional excess hedging or refusal.
  - **Loose calibration**: the confidence it states does not reliably match how reliable it is.

### 1. Next Token Prediction
- Closer to a **very sophisticated autocomplete than a search engine**. It writes based on what tends to follow what. That gives both **fluency** and **hallucination**.
- **Capability zone**: patterns seen many times (summarising, reformatting, explaining common concepts).
- **Limitation zone**: novel or sparse topics, and tasks that need telling **"true" from "sounds true"**.
- **Fabrication concentrates in specifics**: names, dates, statistics, citations, URLs, quotes.
- **Mitigations**: ask for citations, ask it to signal uncertainty, constrained generation, generator-verifier loops (a second check on the output).
- Same prompt in a fresh chat can give a different answer (**sampling variation**).

### 2. Knowledge
- The model knows **only what it saw in training**. There is no live browsing by default, and there is a hard stop at the **knowledge cutoff**.
- **Capability zone**: frequent, consistent topics that were current in the training data. **Limitation zone**: rare, niche, local, contested or post-cutoff topics (e.g. a small country's newest tax rule).
- Typical failures: **staleness**, **uneven coverage**, **inherited bias** about what counts as the "default", and **source amnesia** (it can't say where a fact came from).
- **Fixes**: web search, **retrieval (RAG, MCP connectors)**, tool use.

### 3. Working Memory
- Everything the model can attend to sits in a **fixed-size context window**. Anything outside it simply doesn't exist for the model.
- It is a **cliff, not a gradient**: the failure is **silent truncation**.
- The model **does not learn from your corrections**. It only responds to what is currently in context, and a **new conversation starts from zero**.
- **Limitation zone**: very long documents or chats, continuity across sessions, and key information buried in the **middle** of the input.
- **Fixes**: **front-load** important information, **chunk** long inputs, **re-supply** critical context. Product features help too: memory, compaction, projects, larger windows, multi-agent workflows.

### 4. Steerability
- The model follows instructions by **continuing a pattern** (next-token prediction). Fine-tuning taught it to follow instructions, but the limits come from **pattern-matching, not understanding**.
- **Tightest control**: short, concrete, verifiable instructions (format, length, explicit role). **Loosest**: long reasoning chains, abstract or ambiguous requests, and precise maths or logic done "in its head".
- Failures:
  - **Reasoning drift**: small errors compound over many steps.
  - **Letter over spirit**: the instruction is obeyed literally but the intent is missed.
  - **Brittle arithmetic**.
- **Fixes**: **restate the goal** (repeating the instruction more forcefully doesn't help), add **checkpoints** in multi-step tasks, use system prompts, **code execution**, visible reasoning and structured outputs.

### When properties collide
- Real-world failures are usually **two properties interacting**, not one:
  - Next Token Prediction + Knowledge → **hallucinated specifics** (e.g. a fake citation or a fake IFRS paragraph number). Fix: **verify the specifics**.
  - Working Memory + Steerability → **long-conversation drift** (it forgets earlier rules). Fix: **re-supply the context**.
  - The other named patterns are **confidently wrong maths** (fix: **offload to code execution**) and **agreeing with a bad premise** (sycophancy; fix: **invite pushback**).
- **Diagnostic routine**: notice the unexpected output → name the property (or pair) behind it → place the task on the continuum → apply the matching fix.

## Things an interviewer can ask
- Name the four properties and explain what "capability-to-limitation continuum" means.
- Why is a model "more like autocomplete than a search engine", and where do fabrications concentrate?
- What comes from pre-training and what comes from fine-tuning? Name two "fingerprints" of fine-tuning.
- A colleague says "I corrected it yesterday, so it knows now". Why is that wrong?
- An AI tool gives a wrong total on a VAT reconciliation, cites a non-existent standard, and agreed with your wrong assumption. Diagnose each and pick a fix.
