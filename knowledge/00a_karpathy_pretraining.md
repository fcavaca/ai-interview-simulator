# Karpathy, "Deep Dive into LLMs like ChatGPT", part 1: pre-training
Source: https://www.youtube.com/watch?v=7xTGNNLPyMI (Andrej Karpathy, 3.5 h)

## The three training stages (overview)
1. **Pre-training**: learn from internet text, producing a **base model**.
2. **Supervised fine-tuning (SFT)**: learn from example conversations, producing an **assistant**.
3. **Reinforcement learning (RL)**: practise on problems, producing a **reasoning/"thinking" model**. RLHF is a limited form of this step.

Karpathy's school analogy: textbook **exposition** = pre-training; **worked examples** = SFT; **practice problems** with only the final answer given = RL.

## Step 1: download and filter the internet
- Goal: a huge quantity of **high-quality, diverse** text. Example: Hugging Face's **FineWeb** dataset, about **44 TB** and **15 trillion tokens**. Not that big, because it is aggressively filtered text only.
- Starting point: **Common Crawl** (2.7 billion web pages indexed by 2024).
- Filtering pipeline:
  - **URL filtering** (block-lists of malware, spam, marketing, racist and adult sites)
  - **text extraction** from HTML
  - **language filtering** (e.g. keep pages that are >65% English; this design choice decides which languages the model will be good at)
  - deduplication
  - **PII removal** (addresses, social security numbers)

## Step 2: tokenisation
- Neural networks need a 1-D sequence of symbols from a finite vocabulary. There is a trade-off between **vocabulary size and sequence length**, because sequence length is a precious resource.
- Raw text becomes bytes (256 symbols), then **byte-pair encoding (BPE)** repeatedly merges frequent pairs into new symbols. GPT-4 uses about **100,277 tokens**. Tool to explore: Tiktokenizer.
- Tokens are case- and space-sensitive chunks ("hello world" = 2 tokens). Token IDs are just labels with no numeric meaning.

## Step 3: neural network training
- Take random **windows of tokens** (the context, e.g. up to 8,000 tokens) and train the network to **predict the next token**. The output is a **probability for every token in the vocabulary**.
- Start with **random parameters**, then nudge them so the correct next token becomes more likely. This is repeated in parallel over billions of tokens.
- **Loss** is a single number for how wrong the predictions are; researchers watch it fall during training.
- Inside: a **transformer**, a big but fixed mathematical expression mixing inputs with **parameters/weights** (billions of them, "knobs on a DJ set"). It contains embeddings, **attention** and MLP blocks. These artificial "neurons" are much simpler than biological ones and have **no memory (stateless)**.
- **Compute**: training runs on **GPUs** (e.g. NVIDIA H100s, about $3/GPU-hour to rent), which are suited to parallel matrix maths. Big labs use data centres with 100,000+ GPUs. This GPU "gold rush" drove NVIDIA's valuation.
- Example: **GPT-2** (2019) had 1.6B parameters, a 1,024-token context and 100B training tokens, and cost about $40k to train then (about $600 or less today). **Llama 3** has 405B parameters and 15T tokens. Modern models have hundreds of billions to trillions of parameters and contexts of 100k–1M tokens.

## Step 4: inference
- Generating text: feed a prefix, get probabilities, **sample** a token (flip a biased coin), append it, repeat.
- It is **stochastic**: the same prompt gives different outputs. The output is a "remix" that is statistically similar to the training data, not copied.
- When you chat with ChatGPT, it is **only inference**. Parameters are fixed; no learning happens.

## The base model
- The result of pre-training is a **base model**: an **"internet document simulator"** or very expensive **autocomplete**. Ask it "what is 2+2" and it rambles on instead of answering.
- Its parameters are a **lossy compression of the internet**, like a zip file but lossy. Its knowledge is **vague, probabilistic recollection**: frequent facts are remembered better than rare ones.
- **Regurgitation**: it can recite high-quality, often-seen text (e.g. a Wikipedia page) word for word. This is usually undesirable.
- After the **knowledge cutoff** it guesses. Prompted about events it never saw, it hallucinates "parallel universes".
- **In-context learning / few-shot prompting**: give a pattern (e.g. 10 English→Korean word pairs) and the base model continues it, so apps can be built from clever prompts. A whole assistant can even be faked by formatting the prompt as a human/assistant conversation.
- **Releasing a model** = the code (the forward pass, a few hundred lines) plus the **parameters** (billions of numbers), which are where the value lies.

## Things an interviewer can ask
- What are the three training stages, and what does each produce?
- What is a token, why use BPE, and what is the vocabulary/sequence-length trade-off?
- What does the network actually learn to do during pre-training? What is "loss"?
- Why is a base model not yet useful as an assistant?
- Why is the model's knowledge described as a "lossy compression" or "vague recollection"?
