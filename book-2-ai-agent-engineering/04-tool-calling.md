# 04 — Tool Calling

A tool is a normal function made available to the model.

    def add_numbers(a, b):
        return a + b

The model may request a tool. The application—not the model—executes it.

## Flow
1. Send the user request and tool descriptions.
2. Model returns text or a structured tool request.
3. App validates tool name and arguments.
4. App runs the approved function.
5. App sends result to the model.
6. Model responds.

## Validation
Check:
- Is this tool allowed?
- Are arguments present and correctly typed?
- Are values within limits?
- Does this require user confirmation?

Use narrow tools. A calculator should not have permission to delete files.

Conceptual dispatch:

    if requested_tool in allowed_tools:
        validate_arguments()
        result = run_approved_tool()
    else:
        reject_request()

This is pseudocode; real applications need robust validation and exception handling.

## Failures
Catch errors, report safe messages, avoid pretending success, and stop after repeated failures.

## Exercise
Create a calculator that only supports addition and subtraction. Test valid inputs, missing values, and unsupported operations.