# Word embeddings (IBM Technology)
Source: https://www.youtube.com/watch?v=wgfSDrqYMJ4

## Key points
- An **embedding** represents a word (or text) as a **numeric vector**, positioned so that words with similar meanings lie close together. Distance and direction encode similarity. Example: "apple" is near "orange", while "happy" and "sad" point in opposite directions.
- Why: most ML algorithms cannot process raw text and need numbers.
- Uses in **NLP** (natural language processing):
  - text classification (spam detection, topic categorisation)
  - **named-entity recognition** (finding people, places, organisations)
  - word similarity and analogies (king : queen = man : woman)
  - question answering, clustering similar documents, recommendations
- How they are made: train a model on a large corpus (e.g. Wikipedia). The pipeline is: preprocess (tokenise, remove stop-words and punctuation), then slide a **context window** to pair target and context words, then train the model to predict words from context and adjust its parameters to minimise prediction error. Real embeddings have **hundreds of dimensions**, not 3.
- Two families:
  - **Frequency-based**, e.g. **TF-IDF** (term frequency × inverse document frequency). It scores words that are frequent in one document but rare across the corpus ("espresso" in a coffee article), while "the" and "and" score low.
  - **Prediction-based**: learn semantic relationships from context (dog ↔ bark, wag, tail) and handle close meanings well. Example: **word2vec** (Google, 2013), with two architectures:
    - **CBOW** predicts the target word from its context.
    - **Skip-gram** predicts the context from the target word.
  - **GloVe** (Stanford, 2014) uses global co-occurrence statistics across the whole corpus.
- **Contextual embeddings** (transformers): classic embeddings give each word one fixed vector, but transformers give a word a different vector depending on its context. Example: "bank" for money vs the "bank" of a river.

## Things an interviewer can ask
- What is an embedding and why do models need one?
- TF-IDF vs prediction-based embeddings: what is the difference?
- Why are contextual embeddings an improvement over word2vec?
