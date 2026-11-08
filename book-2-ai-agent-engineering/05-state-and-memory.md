# 05 — State and Memory

State is information the application keeps during a task: current workflow step, conversation, selected language, or temporary results.

## Types
- Current request context.
- Conversation history.
- Temporary session state.
- Long-term memory saved across sessions.
- External knowledge retrieved from documents.

Do not save everything automatically. Store only useful information, respect privacy, and allow inspection or deletion when appropriate.

## Summaries
Long conversations may exceed the model's context window. Summaries can preserve key points, but they may lose details. Keep exact values separately when precision matters.

## Persistence
Temporary state disappears when a process ends. Persistent state is stored in a database or file. SQLite is a useful beginner database.

Never store passwords as plain text; use established authentication systems.

## Exercise
Design a study assistant that remembers the current topic, completed lesson, and next lesson. Decide what should not be stored.