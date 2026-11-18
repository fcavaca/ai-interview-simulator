# Vector databases (IBM Technology)
Source: https://www.youtube.com/watch?v=t9IDoenf-lo

## Key points
- How databases evolved:
  - **SQL** (structured data in tables)
  - **NoSQL** (unstructured documents; real-time web and big data)
  - **graph** databases (nodes and relationships)
  - **vector databases** (built for AI applications)
- A **vector** is an array of numbers that represents a complex object such as text, an image, a document or audio. **Embeddings** are these vectors stored in a multi-dimensional space, so that similar items are grouped together.
- Use cases:
  - chatbots and NLP (semantic understanding, e.g. "car" is related to "engine")
  - image, video and voice recognition (sound waves as numbers, compared for similarity)
  - **similarity search** and recommendation engines
- Benefits over storing vectors in SQL or NoSQL databases:
  1. **Flexibility**: any unstructured data type can be inserted without heavy preparation.
  2. **Scalability**: millions or billions of vectors.
  3. **Speed and performance**: vectors are indexed for fast, low-latency similarity queries.
- An LLM application uses the vector database as an external, searchable store of knowledge. This is the basis of **RAG** and of agents' **long-term memory**.
- Architecture advice: be **polyglot**, i.e. use several database types side by side, each for what it does best.

## Things an interviewer can ask
- What is stored in a vector database and how is it searched?
- Why use a vector database rather than SQL for semantic search?
- How do embeddings, vector databases and RAG connect?
