# 11 — Projects and Capstone Roadmap

Projects turn theory into skill. Complete them in order and write a short report for each.

## Project 1 — Python data tools
Create a grade analyzer or CSV summary program. Practice functions, validation, lists, and files.

## Project 2 — Math toolkit
Implement vector addition, dot product, matrix multiplication, and mean using Python/NumPy. Test against hand-calculated examples.

## Project 3 — Linear regression
Generate simple synthetic data, train using gradient descent, plot loss, and compare predicted values with targets.

## Project 4 — Perceptron
Implement a single neuron for a linearly separable classification task. Explain why it cannot solve XOR alone.

## Project 5 — Neural network from scratch
Implement a small multilayer network using NumPy:
- parameter initialization,
- forward pass,
- loss calculation,
- backpropagation,
- gradient descent,
- training loop,
- evaluation.

Do not use autograd for this project. Check your gradients with finite differences on a tiny example if possible.

## Project 6 — Handwritten digit classifier
Use a small public dataset such as MNIST or a suitable subset. Split data properly, normalize, train, and inspect mistakes.

## Project 7 — CNN image classifier
Train a CNN on a beginner dataset. Compare with a dense network and report accuracy and failure examples.

## Project 8 — Tiny language model
Train a small character-level or token-level model on text you are allowed to use. Report tokenization, training/validation loss, and sample generations.

## Project 9 — Model deployment
Save a model and create a small local prediction interface. Validate inputs and document dependencies.

## Capstone: your own AI model
Choose a manageable problem and follow this process:
1. Define the problem and success metric.
2. Explain why machine learning is suitable.
3. Collect or select permitted data.
4. Inspect and split data.
5. Build a simple baseline.
6. Train a model.
7. Tune using validation data.
8. Evaluate once on held-out test data.
9. Analyze mistakes and limitations.
10. Package code, model, instructions, and report.

## Capstone report template
- Project name and team members
- Problem statement
- Intended users and limits
- Dataset source and license/permission
- Data preparation
- Baseline
- Model architecture
- Training configuration
- Evaluation metrics
- Error analysis
- Ethical/privacy considerations
- How to run it
- Future improvements

## Partner division
One partner may focus on model implementation and mathematics while the other focuses on data pipelines and experiments, but both should understand the complete project. Swap roles for a later project.