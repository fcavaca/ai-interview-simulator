# AI agents (IBM Research)
Source: https://www.youtube.com/watch?v=F8NKVhkZZWI

## Key points
- **Shift 1: from monolithic models to compound AI systems.**
  - A model alone is limited to its training data and is costly to adapt. Asked "how many vacation days do I have?", it can't know.
  - A **compound AI system** surrounds the model with other components: a database query, output verifiers, query decomposition, tools. It is modular, so it is quicker to adapt than tuning a model. **RAG** is the most common compound system.
- **Control logic**: the path a program follows to answer a query.
  - In most compound systems it is **programmatic**, defined by a human. A vacation-policy RAG always searches the policy database, so a weather question fails.
  - **Agents put the LLM in charge of the control logic.** This is possible because LLMs' reasoning has improved: they can break problems down and plan.
- Think fast vs slow: programmed systems "think fast, act as programmed"; agents "think slow": plan, act, check where they're stuck, and re-plan.
- **Three capabilities of LLM agents**:
  1. **Reason**: plan and reason about each step.
  2. **Act** via **tools**: web or database search, calculator, code, other models, APIs. The model decides when and how to call them.
  3. **Memory**: inner reasoning logs and conversation history, which enable personalisation.
- **ReAct** (Reason + Act) is a popular agent design: think and plan → act (call a tool) → **observe** the result → iterate or adjust the plan → final answer. Example: "how many 2-oz sunscreen bottles for my Florida holiday?" needs vacation days (from memory), forecast sun hours, a health website's dosage, and then maths.
- **Sliding scale of autonomy**:
  - For **narrow, well-defined problems** a programmatic route is more efficient; an agent might loop unnecessarily.
  - For **complex, varied tasks** (e.g. solving GitHub issues) agents pay off.
  - Keep a **human in the loop** while accuracy improves.

## Things an interviewer can ask
- What is a compound AI system, and how is an agent different?
- Name the three capabilities of an agent, and describe the ReAct loop.
- When would you *not* use an agent?
