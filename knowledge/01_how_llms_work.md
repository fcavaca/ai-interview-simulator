# How LLMs work (IBM Technology)
Source: https://www.youtube.com/watch?v=5sLYAQS9sWQ

## Key points
- **GPT** = Generative Pre-trained Transformer. An LLM is a model that generates human-like text (and code).
- An LLM is one kind of **foundation model**: a model pre-trained on huge amounts of unlabelled data with **self-supervised** learning, so it learns general patterns that can be adapted to many tasks. LLMs are foundation models applied to text and text-like data such as code.
- "Large" refers both to the data (up to petabytes of text; 1 GB holds about 178 million words) and to the **parameter count**. A parameter is a value the model adjusts during learning; more parameters allow more complex behaviour. Example: GPT-3 was trained on about 45 TB of data and has 175 billion parameters.
- **LLM = data + architecture + training.**
  - Architecture: a neural network, for GPT a **transformer**, which handles sequences and understands each word in relation to every other word in the sentence.
  - Training: the model learns to **predict the next word**. It starts with random guesses ("the sky is bug") and adjusts its parameters after each iteration to reduce the gap between prediction and the real text, until it reliably predicts "blue".
- **Fine-tuning**: further training on a smaller, task-specific dataset turns a general model into an expert at one task.
- Business uses: customer-service chatbots (freeing humans for complex cases), content creation (emails, articles, posts, scripts), software development (writing and reviewing code).

## Things an interviewer can ask
- What is the difference between a foundation model and an LLM?
- What are the three ingredients of an LLM?
- What is a parameter? What does pre-training teach the model, and what does fine-tuning add?
