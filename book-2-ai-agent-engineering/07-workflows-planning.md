# 07 — Workflows and Planning

A workflow follows a designed sequence:

    step A → step B → step C

An agent loop lets a model choose among permitted actions:

    observe → choose permitted action → execute → observe

Workflows are usually easier to debug. Use an agent loop only when flexibility is useful.

## Planning
Break a task into:
- Goal.
- Small steps.
- Required inputs.
- Approved tools.
- Success condition.
- Failure and stop conditions.

A model's plan is only a proposal. The application enforces limits.

## Stop conditions
Set a maximum number of steps, time or cost limit, success condition, and repeated-failure behavior. Never build an endless loop.

## Human approval
Ask before sending messages, publishing, changing account settings, deleting important data, or purchasing. For practice, use mock tools.

## Exercise
Build a fixed workflow: receive topic → search local notes → draft summary → show draft for review. Do not publish automatically.