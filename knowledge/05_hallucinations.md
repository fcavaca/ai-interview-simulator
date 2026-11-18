# Hallucinations (IBM Technology)
Source: https://www.youtube.com/watch?v=cfqtFvWOfg0

## Key points
- A **hallucination** is an LLM output that departs from the facts or from contextual logic: plausible-sounding but wrong. It can be a minor inconsistency or a complete fabrication. Example: Google Bard's launch demo wrongly claimed that the James Webb telescope took the first picture of an exoplanet.
- Types, from simplest to broadest:
  1. **Sentence contradiction**: contradicts its own earlier sentence.
  2. **Prompt contradiction**: contradicts the request (you ask for a positive review and get a negative one).
  3. **Factual contradiction**: a plain factual error.
  4. **Nonsensical or irrelevant** content added.
- Why they happen. The process is partly a black box, but common causes are:
  1. **Data quality**: training data (e.g. scraped web, Reddit) contains noise, errors, biases and gaps, and the model generalises without being able to verify facts.
  2. **Generation method**: decoding methods and objectives (beam search, sampling, maximum likelihood, reinforcement learning) trade off fluency vs diversity and accuracy vs novelty. For example, beam search favours probable but generic words.
  3. **Input context**: unclear, inconsistent or missing context misleads the model. Example: "Can cats speak English?" is answered differently if you mention you mean Garfield.
- Better reasoning ability tends to reduce hallucinations.
- How to reduce them as a user:
  1. **Clear, specific prompts** with detail about what you want.
  2. **Active mitigation through settings**, e.g. a **lower temperature** gives more focused, conservative output, while a higher temperature is more creative but hallucinates more.
  3. **Multi-shot (few-shot) prompting**: give several examples of the desired output so the model recognises the pattern and format.

## Things an interviewer can ask
- Define a hallucination and give the four types.
- Give three causes and three mitigations.
- What does temperature control, and how does it relate to hallucination?
- For accounting: why must AI-generated figures or citations be verified before use?
