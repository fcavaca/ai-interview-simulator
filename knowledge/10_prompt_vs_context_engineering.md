# Prompt engineering vs context engineering (IBM Technology)
Source: https://www.youtube.com/watch?v=vD0E3EUb8-8

## Key points
- **Prompt engineering** is crafting the input text: instructions, examples and formatting cues that steer the output.
- **Context engineering** is the broader, *system-level* discipline of **programmatically assembling everything the LLM sees** at inference: prompts, but also retrieved documents, memory, state and tools.
- Example ("Agent Graeme", a travel agent):
  - "Book a hotel in Paris for the conference" gets booked in Paris, *Kentucky*. That is a vague prompt, but also missing context: the agent could have checked the calendar or the conference site with a tool.
  - Next it books the €900/night Ritz, because the **company travel policy** wasn't in its context.
- Prompt-engineering techniques:
  1. **Role assignment** ("You are a senior Python developer reviewing for security…").
  2. **Few-shot examples**: show 2–3 input/output pairs (show, don't tell).
  3. **Chain-of-thought** ("think step by step"): less needed now that reasoning models are trained with RL.
  4. **Constraint setting** ("max 100 words", "only use the provided context").
- Context-engineering components:
  - **Memory**: short-term (summarising long chats to fit the context window) and long-term (vector database of preferences and past interactions).
  - **State management**: where are we in a multi-step task (did the flight booking succeed? arrival time?).
  - **RAG** with **hybrid search** (semantic + keyword), returning only the relevant sections of a policy.
  - **Tools**, with clear tool descriptions: what each does, when to use it, and its constraints.
  - **Dynamic prompts**: a template filled at runtime. The final prompt may be ~80% dynamic content and ~20% static instructions.
- Summary: prompt engineering gives better questions; context engineering gives better systems.

## Things an interviewer can ask
- Define each and give the difference in one sentence.
- Name four prompt-engineering techniques.
- What did the agent lack when it booked the wrong Paris and the expensive hotel?
