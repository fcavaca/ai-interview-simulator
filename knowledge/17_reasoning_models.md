# Large reasoning models, LRMs (IBM Technology)
Source: https://www.youtube.com/watch?v=enLbj0igyx4

## Key points
- An **LLM** predicts the next token by statistical pattern matching, as a reflex. An **LRM** (large reasoning model) also predicts tokens, but **thinks before it talks**: it plans, weighs options and checks calculations before writing the answer, using an internal **chain of thought**.
- The reflex is fine for a fun social-media post. Reasoning helps with multi-step problems like debugging a stack trace or tracing cash flows through shell companies: test hypotheses, discard dead ends.
- How LRMs are built:
  1. Start from an LLM after massive **pre-training** (web, books, code), which gives language and broad knowledge.
  2. **Reasoning-focused fine-tuning** on curated logic, maths and coding problems with full chain-of-thought answer keys. The model learns to show its work: problem → plan → steps → solution.
  3. **Reinforcement learning** on new problems, rewarded by humans (**RLHF**, thumbs up or down per step) or by **process reward models** that judge each reasoning step. The model learns to produce thought sequences that maximise reward.
  4. Optionally **distillation**: a larger teacher model's reasoning traces are used to train a smaller or newer model.
- **Inference-time (test-time) compute**: how long the model thinks per question is adjustable. Hard questions get more budget, during which the model may run several chains and vote, backtrack with tree search, or call a calculator, database or code sandbox.
- More thinking costs **compute and money** and adds **latency**, in return for (hopefully) **higher accuracy**. Whether it's worth it depends on the task.
- **Pros**: complex multi-step reasoning, better decisions (internal verification), **less prompt engineering** needed ("think step by step" is built in).
- **Cons**: higher compute cost (VRAM, energy, cloud bill) and slower replies. A regular or smaller LLM may be better for simple tasks.
- The top-scoring models on today's benchmarks are mostly reasoning models.

## Things an interviewer can ask
- What is the difference between an LLM and an LRM?
- How is an LRM trained (fine-tuning on chains of thought, RLHF, process reward models, distillation)?
- What is test-time compute, and what is the trade-off?
- When should a business choose a non-reasoning model?
