# The AI stack: complete AI systems (IBM Technology)
Source: https://www.youtube.com/watch?v=RRKwmeyIc24

## Key points
- The model is only one piece. A useful AI system needs **five layers**, and choices at each one affect **quality, speed, cost and safety**. Example used: an app that helps drug-discovery researchers analyse the latest papers.
  1. **Infrastructure**: LLMs usually need AI hardware (**GPUs**). There are three deployment options:
     - **on-premise** (buy it yourself)
     - **cloud** (rent it and scale up or down)
     - **local** (your laptop, small models only)
  2. **Models**. Choose by:
     - **open vs proprietary**
     - **size**: large vs **small language models** (lighter, fit modest hardware, often specialised)
     - **specialisation**: reasoning, tool calling, code, languages

     Catalogues like Hugging Face list over 2 million models.
  3. **Data**: models have a **knowledge cutoff** and are trained on public data, so you add your own:
     - data sources
     - processing pipelines (pre- and post-processing)
     - **vector databases** (embeddings)
     - **retrieval (RAG)**
  4. **Orchestration**: break the user's request into sub-tasks:
     - **planning/thinking** using the model's reasoning
     - **execution** via tool or function calling
     - **review**: an LLM critiques its own output in feedback loops

     A fast-moving layer (MCP, new agent architectures).
  5. **Application**: what the user touches.
     - **Interfaces**: text in/out, but also images, audio and data. **Revisions and citations** let users edit and check outputs.
     - **Integrations**: feeding inputs from, and pushing outputs into, the tools people already use.
- Understanding all the layers matters even when you buy some of them as a service.

## Things an interviewer can ask
- Name the five layers of the AI stack and give one decision made at each.
- Why can't you just pick the best model and stop there?
- What are the trade-offs between on-premise, cloud and local deployment?
