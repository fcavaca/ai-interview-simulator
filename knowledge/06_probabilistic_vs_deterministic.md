# Probabilistic vs deterministic: AI agents vs business rules (IBM Technology)
Source: https://www.youtube.com/watch?v=i1ZmNUbRGD4

## Key points
- Both automate decisions (approve a refund, flag a transaction), in different ways.
- A **business rule** runs in a rules engine. A human writes explicit logic: IF order < 30 days old AND not a final sale THEN approve the refund.
  - It is **deterministic**: the output is a fixed function of the input, simple Boolean logic, the same answer every time.
- An **AI agent** gets a **goal**, **context** (customer, policy, order history) and **tools**, and works out the steps itself.
  - It is built on an LLM that predicts tokens from a **probability distribution**, so it is **probabilistic**. "Approve" may be most likely, but "deny" still has some probability, and the same request run twice can give different answers.
- When to use **rules**:
  - well-defined decisions with structured inputs (refund policy, loan eligibility, insurance pricing tiers)
  - **regulated work**: the rule that fired *is* the explanation, which is good for **audit**
  - each branch can be unit-tested
  - no AI inference cost
- When to use **agents**: the logic can't be written in advance and judgment about context is needed, because inputs are messy or unstructured (free text, photos) or the case wasn't anticipated (e.g. returning dumbbells "because they are too heavy"). Rules only handle what was anticipated; agents generalise from patterns.
- **Hybrid design** (the recommended answer):
  1. Request goes to the **rules engine first** (cheap, fast). Clear-cut cases are approved or declined directly, and most cases are like that.
  2. Cases the rules can't decide **escalate to an AI agent**, which handles unstructured data and chooses tools itself, e.g. a vision model for a photo or the order system for purchase history.
  3. The agent's recommendation passes through **deterministic guardrails**, e.g. above a threshold amount it goes to a **human in the loop** before the final decision.
- Conclusion: agents have not replaced business rules. The two work best together.

## Things an interviewer can ask
- Define deterministic vs probabilistic and say which one an LLM agent is.
- Why do auditors and regulators like rules engines?
- Design a hybrid flow for approving expense claims or flagging suspicious invoices.
