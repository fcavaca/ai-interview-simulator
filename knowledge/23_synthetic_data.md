# Synthetic data (IBM Technology)
Source: https://www.youtube.com/watch?v=HIusawrGBN4

## Key points
- **Synthetic data** is artificially generated rather than produced by real-world events. It is derived from existing datasets, or from algorithms and models, to **replicate the properties of real data**. The term ranges from simple data synthesis to deep learning models.
- Why: real data is often **scarce** or **sensitive or confidential**, e.g. **financial records** and medical histories.
- Advantages:
  - **cheap** and easy to produce
  - can be **perfectly labelled**, unlike messy real data
- Uses and benefits:
  - training data-hungry ML models on large volumes of labelled synthetic data, then transferring them to real data. Gartner predicted that by 2025 AI would need 70% less real data.
  - domain-specific, high-volume data at reasonable cost
  - probing **fraud-detection** models for weaknesses
  - testing autonomous vehicles on roads that don't exist
  - **reducing bias** present in real datasets (fairer, more trustworthy models)
- **Challenges**: synthetic data can't fully capture the variety of real-world factors or **unanticipated events**. Leicester City won the Premier League in 2015 at 5,000-to-1 odds; no synthetic forecast would have included that.
- **How to generate it**: define the data needed → identify sources → generate to specification. Methods:
  - **manipulate existing data** (add noise, transform it)
  - **GANs** (generative adversarial networks), which learn from real data
  - **statistical generators** that sample from chosen distributions

## Things an interviewer can ask
- Define synthetic data and give two reasons a bank or auditor might use it.
- What are its limitations?
- Name three ways to generate it.
