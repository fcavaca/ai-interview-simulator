# Tool calling (IBM Technology)
Source: https://www.youtube.com/watch?v=h8gMhXYAv1k

## Key points
- **Tool calling** lets an LLM use real-time data and external systems (APIs, databases, code execution), which it cannot reach on its own.
- **Traditional tool calling**:
  1. The client application sends the **messages plus a list of tool definitions** to the LLM.
  2. The LLM **recommends which tool to call** and with which arguments. It does not run the tool itself.
  3. The **application executes** the tool and sends the result back.
  4. The LLM interprets the result and either requests another tool or gives the final answer.
- A **tool definition** has a **name**, a **description** (what it does and when to use it) and its **input parameters**.
- Example: "What is the temperature in Miami?" The LLM asks for the weather API, the app calls it and returns 71°F, and the LLM answers "It's a nice 71 degrees."
- Risk: the LLM can **hallucinate** or produce **incorrect tool calls**.
- **Embedded tool calling**: a library or framework sits between the app and the LLM, holds the tool definitions, **executes the tool calls itself** and **retries** failed calls. This reduces errors from hallucinated calls.

## Things an interviewer can ask
- Walk through a tool-calling loop step by step. Who actually executes the tool?
- What goes into a tool definition, and why does the description matter?
- What can go wrong, and how does embedded tool calling help?
