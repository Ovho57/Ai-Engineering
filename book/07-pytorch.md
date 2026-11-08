# 07 — Deep Learning with PyTorch

## Why PyTorch?
PyTorch provides tensors, GPU support, automatic differentiation, neural-network layers, and optimizers. It lets engineers build larger models without manually deriving every gradient, while the mathematical ideas remain the same.

## Tensors
A tensor is a multidimensional array:
- scalar: 0 dimensions,
- vector: 1 dimension,
- matrix: 2 dimensions,
- higher-dimensional tensor: 3+ dimensions.

Shape describes dimensions. A batch of 32 RGB images of size 64×64 may have shape `(32, 3, 64, 64)` in common PyTorch convention.

## Basic tensor operations
```python
import torch
x = torch.tensor([[1., 2.], [3., 4.]])
print(x.shape)
print(x * 2)
print(x @ x.T)
```
`@` performs matrix multiplication. `T` transposes a 2D tensor.

## Autograd
PyTorch tracks operations when gradients are enabled. Calling `.backward()` calculates derivatives for tracked parameters.
```python
import torch
w = torch.tensor(2.0, requires_grad=True)
loss = (w - 5) ** 2
loss.backward()
print(w.grad)  # derivative: -6
```
The gradient is calculated, not the weight update. An optimizer performs updates.

## A simple model
```python
import torch
from torch import nn

model = nn.Sequential(
    nn.Linear(2, 8),
    nn.ReLU(),
    nn.Linear(8, 1)
)
```
`Linear(2,8)` maps 2 input features to 8 outputs. ReLU introduces nonlinearity. The final layer returns one prediction.

## The training loop
```python
import torch
from torch import nn

X = torch.tensor([[0.,0.],[0.,1.],[1.,0.],[1.,1.]])
y = torch.tensor([[0.],[1.],[1.],[0.]])

model = nn.Sequential(nn.Linear(2, 8), nn.Tanh(), nn.Linear(8, 1), nn.Sigmoid())
loss_fn = nn.BCELoss()
optimizer = torch.optim.Adam(model.parameters(), lr=0.03)

for epoch in range(2000):
    prediction = model(X)          # forward pass
    loss = loss_fn(prediction, y)  # calculate loss
    optimizer.zero_grad()          # clear previous gradients
    loss.backward()                # backpropagation
    optimizer.step()               # update parameters
    if epoch % 200 == 0:
        print(epoch, loss.item())
```
This example is for learning. For real binary classification, `BCEWithLogitsLoss` plus a model without final sigmoid is usually more numerically stable.

## Important training steps
1. Calculate predictions.
2. Calculate loss.
3. Clear old gradients.
4. Backpropagate.
5. Update parameters.

PyTorch accumulates gradients by default, so `zero_grad()` matters.

## Training vs evaluation mode
Some layers behave differently during training and evaluation. Use `model.train()` for training and `model.eval()` for evaluation. For inference, use `torch.no_grad()` when appropriate.

## GPU
A model and its tensors must be placed on compatible devices. Check availability:
```python
device = "cuda" if torch.cuda.is_available() else "cpu"
```
Move both model and data to the chosen device. GPU is helpful for larger workloads but not necessary for early lessons.

## Saving a model
Save model parameters (state dict), and also preserve preprocessing, model configuration, and relevant training metadata. A weight file alone may not explain how to use the model.

## Exercises
Explain tensor vs vector; what autograd does; why gradients are cleared; why train/eval modes exist; how to inspect tensor shapes.

## Project
Reimplement the XOR network using PyTorch. Compare training behavior with your NumPy version and explain what PyTorch automated.