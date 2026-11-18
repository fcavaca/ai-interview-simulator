# Explainable AI, XAI (IBM Technology)
Source: https://www.youtube.com/watch?v=jFHPEQi55Ko

## Key points
- Example: a neural-network **fraud detection** model flags a $100 coffee-shop purchase. Without more information you can't judge whether to trust it. The model is a **black box**, and even its creators can't fully explain a specific result.
- **Explainable AI (XAI)** lets humans understand how a model reached its result, which builds **trust**.
- **Three main methods**. The first two address technology requirements; the third addresses human needs.
  1. **Prediction accuracy**: run simulations and compare XAI output with the training data. Most popular technique: **LIME** (Local Interpretable Model-agnostic Explanations), which explains individual classifier predictions.
  2. **Traceability**: narrow the scope of rules and features so decisions can be traced. Technique: **DeepLIFT** (Deep Learning Important FeaTures), which compares each neuron's activation with a reference neuron to show links and dependencies.
  3. **Decision understanding**: the human factor. Educate teams to overcome distrust, for example with a **dashboard** showing the main factors behind a decision (amount, location…), how much each mattered, and the **minimum change** that would flip the outcome (a counterfactual: how much lower the amount would need to be).
- XAI also helps **troubleshoot and improve** models by monitoring **fairness, quality and drift**. **Model drift**: performance degrades over time because production data differs from training data. XAI can raise alerts, e.g. on a surge of false-positive fraud alerts.
- Uses: financial services (fraud), healthcare (diagnostics, imaging, drug approval), criminal justice.
- Explainability helps meet **regulatory standards** and lets **affected people challenge a decision**.

## Things an interviewer can ask
- What is a black-box model, and why is that a problem in finance or audit?
- Name the three XAI methods, and say what LIME and DeepLIFT do.
- What is model drift and how does XAI help detect it?
- Link to deterministic rules: why are rules engines "explainable by design"?
