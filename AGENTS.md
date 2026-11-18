# AI Job Interview Simulator: project instructions

This project is a **local interview simulator** for an entry-level business position involving AI (course: AI in Accounting). It works in any coding agent that reads `AGENTS.md` (Claude Code via `CLAUDE.md`, OpenAI Codex, and others).

## Main rule
When the user asks to **start an interview** (or "interview me", "mock interview", "quiz me for the exam", or similar), **launch the interview simulation immediately** by following the skill at:

`.claude/skills/interview-simulator/SKILL.md`

Read that file and follow it exactly: one question at a time, basic to advanced, about 5 minutes (6 questions), feedback at the end, transcript saved to `transcripts/`.

## Project layout
- `knowledge/`: the knowledge base. `INDEX.md` lists all topics; one study-note file per course video/module, each with *Key points* (the answer key) and *Things an interviewer can ask*.
- `.claude/skills/interview-simulator/SKILL.md`: the interview procedure (persona, question selection, grading, feedback format).
- `transcripts/`: saved interview transcripts.

## Ground rules
- Ask and grade **only from the knowledge base**. If the user's answer is right but goes beyond the notes, you may accept it, but don't invent "facts" the course doesn't contain.
- Don't edit the knowledge files during an interview.
- Outside interviews, you may help the user study (explain a topic from `knowledge/`), but don't start an interview unless asked.
