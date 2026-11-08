# 02 — Python Programming for AI

Python is popular in AI because it is readable and has a rich scientific ecosystem.

## Running Python
Save `hello.py` and run `python hello.py`:
```python
print("Hello, AI!")
```
You can also use VS Code, Jupyter notebooks, or Google Colab.

## Variables and types
```python
name = "TinyNet"
epochs = 10
learning_rate = 0.01
training = True
print(type(learning_rate))
```
Python is dynamically typed: names refer to objects without requiring type declarations.

## Strings and collections
```python
model = "TinyNet"
print(f"Training {model}")
features = [1.2, 0.7, 3.4]
features.append(2.1)
config = {"lr": 0.01, "epochs": 100}
print(config["lr"])
```
Lists are ordered collections; dictionaries associate keys with values.

## Functions
```python
def mean(values):
    if not values:
        raise ValueError("Empty list")
    return sum(values) / len(values)
```
A function should have a clear responsibility. Avoid silently accepting invalid inputs.

## Classes
A class defines objects with data and behavior:
```python
class Neuron:
    def __init__(self, weight, bias):
        self.weight = weight
        self.bias = bias
    def calculate(self, x):
        return self.weight * x + self.bias

n = Neuron(2.0, 1.0)
print(n.calculate(3.0))  # 7.0
```
`__init__` initializes; `self` refers to the instance. Later, classes can represent layers and models.

## Errors and modules
```python
try:
    value = float(input("Number: "))
except ValueError:
    print("Please enter a valid number")
```
Import modules with `import math`. Avoid catching every exception without a reason.

## Virtual environments
Create an isolated package environment:
```bash
python -m venv .venv
```
Windows PowerShell activation: `.venv\\Scripts\\Activate.ps1`. Install with `python -m pip install numpy`. Environments prevent one project's packages from interfering with another.

## NumPy
```python
import numpy as np
x = np.array([1.0, 2.0, 3.0])
print(x.mean())
print(x * 2)
```
NumPy arrays support efficient numerical operations, unlike ordinary lists.

## Plotting
```python
import matplotlib.pyplot as plt
plt.plot([1,2,3], [0.9,0.6,0.3])
plt.xlabel("Epoch")
plt.ylabel("Loss")
plt.show()
```
Plots help us observe training.

## Exercises
Write an average function; create a class storing inputs and labels; find maximum of a list; explain virtual environments; multiply a NumPy array by 10.

## Mini-project
Build a grade analyzer reporting min, max, mean, and count. Handle an empty list correctly.