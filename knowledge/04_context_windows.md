# Context windows (IBM Technology)
Source: https://www.youtube.com/watch?v=-QVoIxEpFkM

## Key points
- The **context window is the LLM's working memory**: the maximum amount of text (prompts, responses and everything else) the model can consider at once.
- When a conversation grows longer than the window, the earliest parts fall out. The model no longer "remembers" them and starts making educated guesses, which can cause **hallucinations**.
- Context is measured in **tokens**, not words. A token can be a character, part of a word, a whole word or a short phrase. Examples:
  - "a" in "drove a car" is its own token.
  - "amoral" becomes "a" + "moral" (two tokens).
  - The "a" in "cat" is not a separate token.

  The **tokenizer** converts text to tokens, and tokenizers differ. Rule of thumb: about **1.5 tokens per English word**.
- **Self-attention** computes how relevant each token is to every other token. The window size is the maximum number of tokens the model can attend to at once.
- Window sizes grew from about 2,000 tokens in early LLMs to 128,000 (IBM Granite 3) and more.
- What fills the window besides the chat itself: the hidden **system prompt** (conditions behaviour), **attached documents** and code, and **retrieved data from RAG**.
- Problems with long windows:
  1. **Compute scales quadratically**: double the tokens and you need about 4× the processing, because every token is related to every preceding token.
  2. **Performance drops**: models do best when the relevant information is at the beginning or end of the context and worst when it is in the **middle** (a 2023 "lost in the middle" study).
  3. **Safety**: a longer input is a bigger attack surface, because malicious instructions can be hidden deep inside it (jailbreaks, prompt injection).

## Things an interviewer can ask
- What is a token, and roughly how many tokens are 100 words?
- What happens when a conversation exceeds the context window?
- Name three things besides the user's messages that use up context.
- Why is a bigger context window not always better?
