# Transformers (IBM Technology)
Source: https://www.youtube.com/watch?v=ZXiruGOCn9s

## Key points
- A transformer **transforms one sequence into another**, for example an English sentence into French. GPT-3 is an **auto-regressive** transformer: it generates text one token at a time, each based on what came before.
- Two parts:
  - The **encoder** works on the input sequence. Its layers produce encodings that capture which parts of the input are relevant to each other.
  - The **decoder** uses those encodings to generate the output sequence.
- Translation is not a word-by-word lookup, because word order and phrasing differ between languages. Transformers do **sequence-to-sequence learning**.
- **Training is semi-supervised**: unsupervised pre-training on a large unlabelled dataset, then supervised fine-tuning to improve performance.
- What is new compared with **recurrent neural networks (RNNs)**: RNNs must process words in order. Transformers use an **attention mechanism** that gives each word context from the rest of the sequence, so they can process in **parallel**. This greatly speeds up training and is the main reason they scaled.
- Uses: translation, document summaries, writing new documents, and even chess and image processing (rivalling convolutional neural networks).

## Things an interviewer can ask
- What does the attention mechanism do, and why does it make transformers faster to train than RNNs?
- What are the encoder and decoder for?
- What does "auto-regressive" mean?
