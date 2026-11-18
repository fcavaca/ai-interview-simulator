# Karpathy, "Deep Dive into LLMs like ChatGPT", part 2: SFT and "LLM psychology"
Source: https://www.youtube.com/watch?v=7xTGNNLPyMI

## Supervised fine-tuning (SFT): making an assistant
- Same algorithm as pre-training; **only the dataset changes**, to **conversations** between a human and an assistant. The assistant is **programmed by example**, not by code.
- Much cheaper: pre-training takes about **3 months** on thousands of GPUs, while SFT takes hours.
- Conversations are turned into tokens with special tokens like `<|im_start|>user … <|im_end|>`. These are new tokens introduced in post-training to mark turns. In the end everything is still a 1-D token sequence.
- **Where the data comes from**: human **labellers** (e.g. via Upwork or Scale AI, as in OpenAI's **InstructGPT** paper, 2022) write prompts and **ideal responses** following long **labelling instructions**: be **helpful, truthful and harmless**. Today much of this data is **synthetic**: LLMs draft and humans edit (e.g. the UltraChat dataset with millions of conversations).
- **What are you talking to in ChatGPT?** Roughly, a **statistical simulation of an expert human labeller** following the company's instructions. It is not a magical AI researching your question.

## Hallucinations: why and how they are mitigated
- **Why**: in training data, "Who is X?" is always answered confidently, so the model imitates that confident style even for unknown names (e.g. made-up facts about a fictional "Orson Kovats"). It samples a plausible guess rather than saying "I don't know".
- **Mitigation 1: teach it to say "I don't know"** (e.g. Meta's Llama 3 "factuality" work):
  1. Generate questions from documents.
  2. Ask the model several times.
  3. Use an LLM judge to compare its answers with the truth.
  4. Where it is wrong, add training examples whose correct answer is "I don't know". This wires the model's internal "uncertainty" signal to an honest refusal.
- **Mitigation 2: tools, e.g. web search.** The model emits special tokens like `[SEARCH_START] query [SEARCH_END]`. The program pauses, runs the search, and pastes the results **into the context window**. The model then answers with **citations**. Tool use is also taught through example conversations.
- **Key mental model**:
  - Knowledge **in the parameters** = **vague recollection** (like something you read a month ago).
  - Knowledge **in the context window** = **working memory**, directly accessible.
  - So **paste the source** (e.g. the chapter you want summarised) instead of relying on memory. Results will be better.

## Knowledge of self
- The model has **no persistent self**: it boots up, processes tokens, and forgets. Asking "who are you?" gives a statistical guess. Old models often claim to be ChatGPT because of how often ChatGPT appears in internet text.
- The identity is **bolted on**, either through hard-coded training conversations (e.g. 240 examples in the OLMo model) or through a hidden **system message**.

## "Models need tokens to think"
- Each token gets a **fixed, small amount of computation** (a finite number of layers). The model can't do a big calculation inside a single token.
- So good answers **spread reasoning over many tokens**, with intermediate steps before the final answer. Training data that states the answer first and justifies it afterwards teaches the model to guess.
- Asked for the answer in one token, the model fails on harder sums.
- **Use tools** (e.g. "use code") for arithmetic and **counting**. Python is more reliable than the model's "mental arithmetic".
- **Spelling and character tasks are weak** because the model sees **tokens, not letters**. That is why "how many r's in strawberry" famously failed.
- **"Swiss cheese" capabilities**: brilliant at Olympiad maths, yet it can fail at "is 9.11 > 9.9?" (possibly confused by Bible-verse numbering). The holes are random, so **use LLMs as tools, check their work, and own the result**.

## Things an interviewer can ask
- What changes between pre-training and SFT? Where does SFT data come from?
- Why do LLMs hallucinate, and what are two mitigations?
- What is the difference between knowledge in the parameters and knowledge in the context window? What does that imply for prompting?
- Why are LLMs bad at counting and spelling? What is the fix?
- What does "Swiss-cheese capabilities" mean for using LLMs in accounting?
