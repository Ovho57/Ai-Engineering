# 06 — Neural Networks from Scratch

## 6.1 Why neural networks?
A neural network is a parameterized mathematical function made from connected units called neurons. Training adjusts its parameters—weights and biases—so its predictions improve on examples.

## 6.2 A neuron
For inputs x₁,…,xₙ, weights w₁,…,wₙ, and bias b:

`z = w₁x₁ + w₂x₂ + ... + wₙxₙ + b`

Then an activation function produces `a = φ(z)`. The weights determine how strongly inputs influence the neuron; the bias shifts its response.

Example: x=[2,3], w=[0.5,−1], b=2. Then z=0.5(2)−1(3)+2=0. If activation is ReLU, output is 0.

## 6.3 Activation functions
Without nonlinear activations, stacking linear layers still produces a linear function. Nonlinearity lets networks learn more complex relationships.

- **ReLU:** `max(0,z)`. Simple and common; negative inputs output zero.
- **Sigmoid:** `1/(1+e^(−z))`. Output between 0 and 1; can saturate.
- **Tanh:** output between −1 and 1; can saturate.
- **Softmax:** converts a vector of scores into values summing to 1:

`softmax(zᵢ)=exp(zᵢ)/Σⱼ exp(zⱼ)`

Softmax is often used for mutually exclusive classes. In code, use numerically stable library implementations.

## 6.4 Layers and shapes
An input layer represents features; hidden layers transform representations; output layer produces predictions. “Layer” often means a collection of neurons calculated together.

For a batch with shape `(batch_size, input_features)`, a dense layer with `output_features` typically has weights shaped `(input_features, output_features)` and biases `(output_features,)`.

## 6.5 Forward propagation
Forward propagation calculates output through the network:
1. take input,
2. calculate weighted sums and biases,
3. apply activations,
4. pass activations to the next layer,
5. calculate final prediction and loss.

A two-layer network:

`H = φ(XW₁ + b₁)`

`Ŷ = ψ(HW₂ + b₂)`

Here X is input batch, W are weights, b are biases, and φ/ψ are activations.

## 6.6 Loss functions
For regression, MSE is common. For classification, cross-entropy is common. The loss turns prediction quality into a scalar objective that training attempts to minimize.

Binary cross-entropy for target y and probability p:

`L = −[y log(p) + (1−y) log(1−p)]`

Avoid evaluating log(0); implementations use stable formulas.

## 6.7 Backpropagation
Backpropagation calculates gradients of loss with respect to every parameter by applying the chain rule from the output layer back toward the input.

Conceptual steps:
1. Forward pass: compute predictions and intermediate values.
2. Compute loss.
3. Find output-layer gradient.
4. Propagate gradient backward through each operation.
5. Obtain gradients for weights and biases.
6. Update parameters using an optimizer.

Backpropagation is not the optimizer. Backprop computes gradients; gradient descent or another optimizer uses them to update parameters.

## 6.8 Gradient descent
For each parameter θ:

`θ ← θ − η ∂L/∂θ`

η is learning rate. Batch gradient descent uses all training examples per update; stochastic gradient descent uses one; mini-batch gradient descent uses a subset and is widely used.

## 6.9 Training vocabulary
- **Epoch:** one complete pass through training data.
- **Batch:** group of examples processed together.
- **Iteration/step:** one parameter update (usage can vary by framework).
- **Learning rate:** update step size.
- **Optimizer:** rule for updating parameters.
- **Initialization:** starting parameter values.

## 6.10 Tiny neuron in NumPy
```python
import numpy as np
x = np.array([2.0, 3.0])
w = np.array([0.5, -1.0])
b = 2.0
z = np.dot(x, w) + b
relu = max(0.0, z)
print(z, relu)  # 0.0, 0.0
```

## 6.11 XOR challenge
XOR outputs 1 when inputs differ and 0 when equal. A single linear neuron cannot represent XOR. A small network with a hidden layer and nonlinear activations can. This demonstrates why hidden layers and nonlinearities matter.

## Common mistakes
- Confusing weights with inputs.
- Forgetting bias.
- Mixing up matrix shapes.
- Updating weights before computing all gradients.
- Learning rate too large.
- Expecting loss to decrease every single batch.
- Thinking backpropagation itself changes weights.

## Exercises
1. Compute a neuron output by hand.
2. Explain why a linear stack is still linear.
3. Explain forward pass vs backward pass.
4. What is the difference between epoch and batch?
5. Why can a single neuron not learn XOR?

## Project
Implement a two-layer neural network for XOR using NumPy. Track loss, train until it learns the four cases, and explain each tensor shape. Do not use a deep-learning framework for this project.