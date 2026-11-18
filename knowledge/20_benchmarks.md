# LLM benchmarks (IBM Technology)
Source: https://www.youtube.com/watch?v=kDY4TodQwbg

## Key points
- An **LLM benchmark** is a standardised framework for assessing LLM performance: it supplies a task, evaluates the output with a metric, and produces a **score** (usually 0–100). Benchmarks are used to **compare models** for a task and to guide **fine-tuning**. Capabilities tested include coding, translation and summarisation.
- **Three steps**:
  1. **Prepare sample data**: documents, coding problems, maths problems.
  2. **Test the model**, using **zero-shot** (no examples), **few-shot** (a few labelled examples) or **fine-tuned** approaches.
  3. **Score**, the most important step. Metrics include:
     - **accuracy** (share of correct answers)
     - **recall** (true positives found)
     - **perplexity** (how well the model predicts text)

     Often several are combined.
- Analogy: track-team trials (200 m, 400 m, 800 m) combined into one score. LLM example: on a science test, model 1 scores 90% accuracy, model 2 70% and model 3 30%, so model 1 is best *for that test*.
- **Limitations**:
  1. May miss **edge cases** and unusual scenarios, so they are not specific enough for your problem.
  2. Can be **too specific**, so models **overfit** to the benchmark, which says little about performance on new data.
  3. **Finite lifespan**: once models max out a benchmark it must be replaced, so new benchmarks keep appearing.

## Things an interviewer can ask
- What are the three steps of running a benchmark?
- Zero-shot vs few-shot testing?
- Why might a model that tops a public benchmark still be a poor choice for your company's task? (Overfitting, edge cases, a different task; test on your own data.)
