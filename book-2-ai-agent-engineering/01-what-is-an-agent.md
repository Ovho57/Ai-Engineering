# 01 — What Is an AI Agent?

An AI agent is a program that uses an AI model to help decide how to complete a task. Depending on its design, it can request tools, observe results, and continue through a controlled sequence.

## Chatbot vs. agent

A simple chatbot:

    user → model → text answer

A tool-using agent:

    user → model → tool request → application runs tool
         → tool result → model → final answer

The model proposes a tool call. **The application validates and executes it.**

## Components
- Model: generates text or decisions.
- Instructions: explain the task and limits.
- Tools: functions the application allows.
- Control loop: manages model/tool steps.
- State: stores relevant task information.
- Evaluation: checks whether it worked.
- Guardrails: restrict allowed actions.

## Example: study helper
A user asks: “What is 12 × 15?”
1. App sends the question to the model.
2. Model answers or requests a calculator.
3. App checks the request.
4. Calculator returns 180.
5. Model explains.
6. App shows the answer.

The calculator should only calculate, not access unrelated files.

## Autonomy
- Level 0: text response, no tools.
- Level 1: one safe, read-only tool.
- Level 2: several limited tools.
- Level 3: bounded multi-step tasks with checkpoints.

Start at Level 0 or 1. Add capabilities only after testing.

## When to use agents
Agents help when a task needs natural-language understanding, tool choice, or flexible multi-step work. A simple fixed program is often cheaper and easier to test.

## Exercise
Design a notes-search tool and a calculator tool. Define what each can and cannot do, and how the app checks requests.