# AI Job Interview Simulator

Practice tool for an interview for an entry-level business position involving AI (course: *AI in Accounting*). It comes in two versions.

## 1. Website version (simple)
`index.html`, hosted on GitHub Pages. It asks **two questions** (basic, then harder) on random course topics, waits for each answer, then gives feedback. It calls Google's Gemini API directly from your browser: paste your own free key from [aistudio.google.com/apikey](https://aistudio.google.com/apikey). The key never leaves your browser except to Google.

## 2. Project version (local, full interview)
Open this folder in a coding agent that reads `AGENTS.md` / `SKILL.md` (e.g. **Claude Code** or **OpenAI Codex**) and type:

> start an interview

The agent follows `.claude/skills/interview-simulator/SKILL.md`: a ~5-minute interview with **6 questions, one at a time**, going from basic to advanced (business and accounting scenarios). It ends with feedback on **strengths, knowledge gaps and incorrect answers**, plus what to review. The transcript is saved to `transcripts/`.

| File | Purpose |
|---|---|
| `AGENTS.md` | Project instructions: "start an interview" launches the skill |
| `CLAUDE.md` | Makes Claude Code load `AGENTS.md` |
| `.claude/skills/interview-simulator/SKILL.md` | Interview procedure: persona, question selection, grading, feedback format |
| `knowledge/` | Knowledge base: one study-note file per course source, plus `INDEX.md` |
| `transcripts/` | Saved interview transcripts |

## Knowledge base
The study notes were written from the full transcripts of the course materials:
- Andrej Karpathy, *Deep Dive into LLMs like ChatGPT* (3 files)
- Anthropic Academy, *AI Capabilities and Limitations* (Coursera)
- 24 IBM Technology videos (LLMs, transformers, context windows, hallucinations, embeddings, vector databases, RAG, prompt vs context engineering, tool calling, MCP, agents, skills, memory, reasoning models, AI stack, prompt injection, benchmarks, LLM-as-a-judge, explainable AI, synthetic data, use-case selection, business rules vs agents)

The notes are summaries in our own words with links to each original video. The raw transcripts are not redistributed.
