# Retrieval-augmented generation, RAG (IBM Research)
Source: https://www.youtube.com/watch?v=T-D1OfcDW1M

## Key points
- Two typical LLM problems, shown with the "which planet has the most moons?" example. From memory the answer is Jupiter; a current source like NASA says Saturn.
  1. **No source**: the answer is given confidently, with no evidence.
  2. **Out of date**: knowledge is frozen at training time.
- **RAG** adds a **content store**, either open (the internet) or closed (company documents, policies). Before answering, the system **retrieves** content relevant to the user's question.
- The prompt then has **three parts**: the **instruction** (use the retrieved content), the **retrieved content**, and the **user's question**. The model generates its answer from these and can **cite evidence**.
- How RAG fixes the two problems:
  - **Up to date** without retraining: update the data store and the next query uses the new information.
  - **Grounded in primary sources**: less hallucination and less leakage of training data.
  - It enables the valuable behaviour of saying **"I don't know"** when the store has no reliable answer.
- Downside: if the **retriever** is poor, the model gets bad or no grounding, and answerable questions go unanswered. So both the retriever and the generator must be improved.

## Things an interviewer can ask
- What are the parts of a RAG prompt?
- Which two LLM weaknesses does RAG address, and why is updating the store cheaper than retraining?
- What happens if retrieval fails?
- For accounting: why ground a policy chatbot in the company's own manuals?
