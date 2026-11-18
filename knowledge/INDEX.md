# Knowledge base index

Study notes written from the course videos (transcripts read in full) and the Anthropic Academy course.
Each file has **Key points** (the answer key) and **Things an interviewer can ask**.

| # | Topic | File | Basic question area | Harder question area |
|---|---|---|---|---|
| 0a | How LLMs are built: pre-training, tokens, inference (Karpathy) | 00a_karpathy_pretraining.md | What is a token? What is a base model? | Why is knowledge a "lossy compression"? Vocabulary/sequence trade-off |
| 0b | SFT, hallucination fixes, "LLM psychology" (Karpathy) | 00b_karpathy_post_training_psychology.md | What is SFT? | Parameters vs context window; "models need tokens to think"; Swiss cheese |
| 0c | RL, thinking models, RLHF, the future (Karpathy) | 00c_karpathy_rl_and_future.md | What is RL in one sentence? | Why RLHF can't run long; verifiable vs unverifiable domains |
| 1 | How LLMs work | 01_how_llms_work.md | Foundation model vs LLM | Pre-training vs fine-tuning |
| 2 | AI, ML, deep learning, generative AI | 02_ai_ml_dl_genai.md | Nesting of the fields | Expert systems vs ML; why deep learning is hard to explain |
| 3 | Transformers | 03_transformers.md | What is a transformer? | Attention vs RNNs; encoder/decoder |
| 4 | Context windows | 04_context_windows.md | What is a context window/token? | Quadratic compute; lost-in-the-middle; attack surface |
| 5 | Hallucinations | 05_hallucinations.md | Define hallucination | Causes and mitigations; temperature |
| 6 | Probabilistic vs deterministic (agents vs business rules) | 06_probabilistic_vs_deterministic.md | Deterministic vs probabilistic | Design a hybrid flow with guardrails and human in the loop |
| 7 | Embeddings | 07_embeddings.md | What is an embedding? | TF-IDF vs word2vec vs contextual embeddings |
| 8 | Vector databases | 08_vector_databases.md | What does a vector DB store? | Why use it instead of SQL for semantic search |
| 9 | RAG | 09_rag.md | What is RAG? | Three prompt parts; retriever failure; "I don't know" |
| 10 | Prompt vs context engineering | 10_prompt_vs_context_engineering.md | Define both | Components of context engineering |
| 11 | Tool calling | 11_tool_calling.md | What is tool calling? | Who executes the tool; embedded tool calling |
| 12 | MCP vs APIs | 12_mcp_vs_api.md | What is MCP? | Dynamic discovery; MCP wraps APIs |
| 13 | AI agents | 13_ai_agents.md | What is an AI agent? | Compound systems, ReAct, autonomy trade-off |
| 14 | Agents in business workflows | 14_agents_business_workflows.md | Why do agent demos fail in production? | Invoice-processing exceptions; four patterns |
| 15 | Agent skills | 15_agent_skills.md | What is a SKILL.md? | Progressive disclosure; skills vs MCP vs RAG vs fine-tuning |
| 16 | Agent memory | 16_agent_memory.md | Four memory types | Why episodic memory is hardest |
| 17 | Reasoning models | 17_reasoning_models.md | LLM vs LRM | How LRMs are trained; test-time compute trade-off |
| 18 | The AI stack | 18_ai_stack.md | Five layers | Deployment and model-choice trade-offs |
| 19 | Prompt injection | 19_prompt_injection.md | What is prompt injection? | Direct vs indirect; defences; least privilege |
| 20 | Benchmarks | 20_benchmarks.md | What is a benchmark? | Limitations: overfitting, lifespan |
| 21 | LLM-as-a-judge | 21_llm_as_judge.md | What is LLM-as-a-judge? | Biases and how to test for them |
| 22 | Explainable AI | 22_explainable_ai.md | What is a black box? | LIME, DeepLIFT, drift, counterfactuals |
| 23 | Synthetic data | 23_synthetic_data.md | Define synthetic data | Benefits vs limits for finance |
| 24 | Selecting AI use cases | 24_selecting_use_cases.md | Is GenAI always the answer? | Four considerations; TCO/ROI |
| 25 | Anthropic Academy: AI Capabilities and Limitations | 25_anthropic_capabilities_limitations.md | Next-token prediction, knowledge, working memory, steerability | Diagnose an unexpected output and pick a fix |
