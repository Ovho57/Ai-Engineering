# 08 — Evaluation, Reliability, and Safety

A successful demo does not prove an agent is reliable.

Test correctness, tool selection, argument validation, missing information, tool failures, cost, latency, and safety limits.

## Test set
Include easy cases, ambiguous requests, invalid inputs, tool errors, out-of-scope requests, and attempts to override instructions. Re-run tests after changes.

## Metrics
- Task success rate.
- Tool-call accuracy.
- Error rate.
- Response time.
- Cost per task.
- Human correction rate.

Do not judge quality using one metric alone.

## Prompt injection
Prompt injection is content attempting to manipulate model instructions, such as a document saying “ignore your rules.”

Defenses:
- Separate trusted instructions from retrieved content.
- Treat documents and tool results as data.
- Validate tool requests in application code.
- Limit permissions.
- Require approval for sensitive actions.
- Test adversarial examples.

## Reliability
Use timeouts, bounded retries, logs that exclude secrets, rate limits, monitoring, and safe fallback behavior.

## Exercise
Write 10 test cases for a notes-search agent, including invalid requests and a tool failure.