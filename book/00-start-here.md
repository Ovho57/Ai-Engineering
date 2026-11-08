# Book 1 — AI Engineering: Machine Learning and Neural Networks

## 00 — How to Use This Book

## What is AI engineering?
Artificial intelligence (AI) is the broad field of making computer systems perform tasks involving prediction, perception, language, or decision-making. AI engineering means designing, implementing, training, evaluating, and operating these systems. This book focuses on machine learning and neural network models, not the separate AI-agent specialization.

Three important activities:
- **Build:** choose and implement a model structure.
- **Train:** use data and an optimization algorithm to adjust its parameters.
- **Evaluate:** test how well it works on examples it did not train on.

## What does “from scratch” mean?
1. Understand the concept and math rather than treating a library as magic.
2. Implement educational models with Python and NumPy, including forward calculations and gradients.
3. Production-level scratch means writing low-level GPU kernels and infrastructure. That is beyond our first goal.

We will later use PyTorch for reliable tensor operations and automatic differentiation while continuing to understand the underlying ideas.

## Roadmap
Computer science → Python → math → data → machine learning → neural networks → deep learning → transformers → model engineering.

Each stage depends on earlier ones: models are programs, use mathematics, learn from data, and are optimized by training.

## Partner study method
For every lesson: Partner A explains; Partner B asks questions; swap roles; solve exercises separately; compare explanations. Teaching reveals gaps. Keep a journal of concepts, examples, confusion, bugs, and questions.

## Expectations
No AI experience is required. Basic arithmetic is enough to start. Algebra, calculus, and probability will be introduced gradually. Mistakes and debugging are part of learning.

## Checkpoint
Explain without looking: (1) build vs train vs evaluate, (2) why Python and math come first, and (3) what scratch means in this course.
