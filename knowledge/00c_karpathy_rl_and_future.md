# Karpathy, "Deep Dive into LLMs like ChatGPT", part 3: reinforcement learning, RLHF, the future
Source: https://www.youtube.com/watch?v=7xTGNNLPyMI

## Why reinforcement learning (RL)?
- Human labellers don't know which solution path is best **for the model**. What is easy for us may be too big a leap for the model, and vice versa, because its cognition is different. SFT is a useful **initialisation**, but the model must **discover its own token sequences** that reliably reach the answer.
- **RL = guess and check**:
  1. For one prompt, sample many solutions (thousands).
  2. Check which ones reach the **correct answer**.
  3. **Train on the successful ones** to reinforce them.

  The data now comes from the model itself, not from humans.
- Pre-training and SFT are standard everywhere. RL is **newer and still maturing**. The **DeepSeek-R1** paper (early 2025) publicly showed how powerful RL fine-tuning is.
- **Emergent "thinking"**: with RL, responses get **longer**, and the model learns to re-check, backtrack and try other angles ("wait, let me re-evaluate…"). These are **cognitive strategies** that nobody programmed. They appear because they increase accuracy. Such models are **reasoning/thinking models** (DeepSeek-R1, OpenAI o1/o3, Gemini "thinking"). Models like GPT-4o are "mostly SFT" plus RLHF.
- Practical advice: use thinking models for hard maths, code and reasoning; use a normal model for simple factual questions, which is faster and cheaper.
- **AlphaGo analogy**: imitating human experts (supervised learning) tops out below the best humans, whereas RL can surpass them. **Move 37** was a move humans estimated at about 1 in 10,000 that proved brilliant. In principle, LLM RL could find reasoning strategies humans haven't found. RL needs a large, diverse set of practice problems.

## RL in unverifiable domains: RLHF
- **Verifiable domains** (maths, code) can be scored automatically against the answer. **Unverifiable** ones (jokes, poems, summaries) can't, and asking humans to score billions of samples is impossible.
- **RLHF** (reinforcement learning from human feedback):
  1. Humans **rank** a few model outputs (ranking is easier than writing).
  2. A separate **reward model** (a neural network) is trained to imitate those rankings, giving a "simulator of human preferences".
  3. Run RL against the reward model.
- **Upside**: RL becomes possible anywhere, and models improve. It exploits the **discriminator–generator gap**: judging is easier than creating.
- **Downside**: the reward model is only a **lossy simulation** of humans, and RL learns to **game** it. After a few hundred steps, nonsense outputs ("the the the the") can get top scores. These are **adversarial examples**. So RLHF must be stopped early. **"RLHF is not RL" in the magical sense**: it is a small fine-tune that can't be run indefinitely, unlike RL with a true verifier (maths answers, Go wins).

## The future (as of early 2025)
- **Multimodality**: audio and images are tokenised too (spectrogram slices, image patches) and handled natively in one model.
- **Agents**: long-running tasks with humans supervising. A **human-to-agent ratio**, like human-to-robot ratios in factories.
- **Computer use**: models acting with keyboard and mouse (e.g. OpenAI Operator).
- AI becomes **pervasive and invisible** inside tools.
- Open research, e.g. **test-time training**. Today parameters are fixed after training and the only learning at use time is **in-context learning**. The context window is finite, so new ideas are needed for very long tasks.

## Keeping up and running models
- **LM Arena**: a leaderboard based on blind human comparisons, though possibly gamed; try models yourself.
- The **AI News** newsletter, and X/Twitter.
- Proprietary models are used on the provider's site. **Open-weights** models (DeepSeek, Llama) can be used via inference providers (e.g. together.ai), or run **locally** in smaller **distilled**, lower-precision versions (e.g. in LM Studio).

## Final message
- What ChatGPT returns is a **token-by-token neural-network simulation of a labeller following the company's instructions**. Thinking models add something new: strategies that emerged from RL.
- **Use LLMs as tools**: for inspiration and first drafts, but **check and verify**, and you remain responsible for the work.

## Things an interviewer can ask
- Explain RL for LLMs as "guess and check". Why can't human labellers just write the best solutions?
- What is a reasoning/thinking model, and what behaviour emerges from RL?
- How does RLHF work? Why can't it be run for long (reward hacking)?
- What does the AlphaGo "move 37" story suggest about RL?
- Verifiable vs unverifiable domains: give an accounting example of each.
