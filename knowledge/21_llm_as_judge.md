# Evaluating AI outputs: LLM-as-a-judge (IBM Research)
Source: https://www.youtube.com/watch?v=trfUBIDeI1Y

## Key points
- Manual labelling of hundreds of outputs is slow, and traditional metrics may not fit. **LLM-as-a-judge** uses an LLM to evaluate other LLMs' outputs.
- Two **reference-free** strategies:
  1. **Direct assessment**: design a **rubric** (e.g. "Is this summary clear and coherent? Yes/No") and score each output against it.
  2. **Pairwise comparison**: "Which is better, A or B?". With many outputs, a ranking algorithm turns the comparisons into a ranking.
- User research with IBM's open-source **EvalAssist** found:
  - about half preferred **direct assessment** (clarity and control over the rubric)
  - about a quarter preferred **pairwise** (especially for subjective tasks)
  - the rest preferred a **combination** (direct for compliance, pairwise ranking to pick the best)

  The best choice depends on the task and the user.
- **Benefits**:
  1. **Scales** to thousands of outputs.
  2. **Flexible**: criteria naturally shift as you see data, and it's easy to refine the rubric or prompt.
  3. **Nuance**: traditional metrics like **BLEU/ROUGE** measure word overlap with a reference. An LLM judge can assess subjective qualities ("does it sound natural?") without a reference.
- **Drawbacks: judge biases**:
  - **Positional bias**: favours whichever option is in a given position (always "A").
  - **Verbosity bias**: favours longer answers even when they are repetitive.
  - **Self-enhancement bias**: favours outputs it generated itself.
- **Mitigation**: e.g. **swap positions** and check whether the verdict changes. Bias doesn't mean the system is broken; it means you must stay vigilant.

## Things an interviewer can ask
- Direct assessment vs pairwise comparison: when would you use each?
- Name three biases of LLM judges, and how you would test for positional bias.
- Why use an LLM judge instead of BLEU/ROUGE?
