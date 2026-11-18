# AI agents in real business workflows (IBM Technology)
Source: https://www.youtube.com/watch?v=4Vg2aVtrX8k

## Key points
- Many agents fail when they move from demo to production. The cause isn't weak technology: real problems are **complex, constrained and interconnected**.
- Real agent problems typically:
  1. span **multiple systems**
  2. involve **policies, approvals and rules**
  3. must fit **existing workflows**
  4. need a **human in the loop**
- So successful agents are not standalone decision-makers but **coordination layers**. They keep context, orchestrate actions across systems, enforce rules, and decide when to hand control to a human.
- Four recurring patterns:
  1. **Multi-step orchestration across systems**, e.g. **employee onboarding** (access, equipment, scheduling, training). It uses signals like role, location and start date, tracks workflow state and flags deviations. The hard part is reliable orchestration under policy and timing constraints, not reasoning.
  2. **Policy-governed action execution**, e.g. **IT support** tickets. The agent interprets intent, checks policy, auto-executes low-risk permitted actions, and **escalates** ambiguous or high-risk ones, giving explicit control boundaries.
  3. **Exception handling in well-defined processes**, e.g. **invoice processing** and order management. The happy path is: extract data → match to records → validate against rules → route approval → update downstream systems. The value lies in handling **missing or mismatched data and non-standard cases**, and in sending only the exceptions to humans.
  4. **Triage and routing at volume**, e.g. **customer service**: categorise, route to teams, suggest replies from history. Humans still resolve the issues, and the agent makes prioritisation consistent at scale.
- Common traits of successful agents: **narrowly scoped**, orchestrate across systems, apply rules, keep humans in the loop, designed for **integration, not isolation**. Their value lies in aligning with workflows, limits and control structures, more than in autonomy.

## Things an interviewer can ask
- Why do many agent demos fail in production?
- Describe how an agent should handle invoice processing. Where is the real value?
- What makes an agent "production-ready"?
