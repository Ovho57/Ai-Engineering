# 02 — LLMs, Prompts, and Context

## What is an LLM?
A large language model is a neural network trained to predict and generate sequences of tokens. Tokens may be words, word pieces, or punctuation.

    text → tokenizer → token IDs → model → token IDs → text

## Prompt
A prompt is the input sent to the model. It may contain instructions, the user's question, relevant context, tools, and conversation history.

Example:

    Instruction: Explain for a beginner.
    User: What is a variable?
    Context: The learner is studying Python.

Clear instructions help, but do not guarantee correctness.

## Context window
The context window is how much information the model can process in a request. It includes instructions, history, tool results, and the current question.

Too much irrelevant context can increase cost and reduce focus. Send relevant information rather than every past message.

## Temperature
Lower temperature generally makes outputs more predictable. Higher temperature usually increases variety. Temperature does not create knowledge or guarantee accuracy.

## Hallucinations
A hallucination is a plausible-sounding but incorrect or unsupported answer.

Reduce risk by supplying reliable context, checking important claims, using deterministic tools for math, and evaluating responses.

Treat documents and retrieved content as data—not instructions that can override the application's rules.

## Exercise
Write a vague prompt and a clear prompt for explaining neural networks. Compare the answers.