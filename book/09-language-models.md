# 09 — Language Models

## What is a language model?
A language model estimates or learns patterns in sequences of tokens. An autoregressive language model predicts the next token based on previous tokens.

`P(tokenₜ | token₁, token₂, ..., tokenₜ₋₁)`

The model does not simply store a dictionary of answers; it learns statistical patterns in training data. This does not guarantee factual accuracy or human-like understanding.

## Tokenization
A tokenizer converts text into token IDs. Tokens may be words, parts of words, characters, or byte sequences. A token is not necessarily a complete word.

Example (illustrative): `"learning AI" → [token_42, token_817]`. Actual IDs depend on tokenizer vocabulary.

## Vocabulary and embeddings
Vocabulary maps token strings to integer IDs. Embeddings map IDs to learned vectors. Similar patterns may lead to related representations, but embedding geometry is not a perfect dictionary of meanings.

## Positional information
Attention alone does not inherently know sequence order. Transformers use positional embeddings or other positional mechanisms to represent order.

## Self-attention
Each token can use information from other tokens. Queries, keys, and values are computed from token representations. Attention scores determine how information is combined.

For causal language modeling, a causal mask prevents a position from seeing future tokens during prediction.

## Next-token training
Training examples are sequences. Inputs might be tokens `[A, B, C]`; targets are shifted tokens `[B, C, D]`. The model learns to predict each next token.

Cross-entropy compares predicted token distributions against the correct next token. Training adjusts weights to reduce this objective.

## Tiny language model workflow
1. Gather a small, lawful, appropriate text corpus.
2. Clean and split the data.
3. Build or choose a tokenizer.
4. Create token sequences and next-token targets.
5. Build a small causal model.
6. Train with cross-entropy and an optimizer.
7. Evaluate on held-out text.
8. Generate text by repeatedly sampling or selecting next tokens.

## Sampling
- **Greedy:** always choose highest-scoring token; can be repetitive.
- **Temperature:** adjusts distribution sharpness; lower values are more conservative, higher values more varied.
- **Top-k:** restrict candidates to k high-scoring tokens.
- **Top-p:** restrict to a probability mass threshold.

Sampling settings change output behavior, not the model's underlying knowledge.

## Fine-tuning and transfer learning
Fine-tuning continues training a pretrained model on a narrower dataset or task. It can adapt behavior but does not guarantee factual correctness. Keep evaluation data separate and avoid training on private or sensitive data without permission.

## Limits and responsible use
Language models can hallucinate, reproduce biases, and fail on unfamiliar situations. Do not treat generated output as automatically true. Respect copyright, privacy, and dataset permissions.

## Exercises
What is a token? Why shift targets? What does causal masking prevent? Compare greedy sampling and temperature. Why use a validation set?

## Project
Train a tiny character-level language model on a small text you have permission to use. Document corpus size, tokenizer, loss, and examples of strengths and weaknesses.