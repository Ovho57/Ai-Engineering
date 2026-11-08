# 05 — Machine Learning

## The idea
Traditional programming uses explicit rules: rules + input → output. Machine learning uses examples and an algorithm to fit a model: training data + learning procedure → trained model. The model predicts on new inputs.

## Types of learning
- **Supervised:** examples include targets (price prediction, spam classification).
- **Unsupervised:** no supplied target; find structure (clustering).
- **Reinforcement learning:** an agent interacts with an environment and learns from rewards.

## Regression vs classification
Regression predicts a quantity; classification predicts a category. A classifier may output class scores or probabilities.

## Linear regression
For one feature: `ŷ = wx + b`. For multiple features: `ŷ = w₁x₁ + ... + wₙxₙ + b`. This resembles a neuron before applying a nonlinear activation.

## Loss
Squared error: `L=(ŷ−y)²`. Mean squared error: `MSE = (1/N) Σ(ŷᵢ−yᵢ)²`. Loss measures error under a particular objective; low loss alone does not guarantee real-world usefulness.

## Gradient descent for linear regression
For prediction `ŷ=wx+b`, squared loss `L=(wx+b−y)²`:
- `∂L/∂w = 2(wx+b−y)x`
- `∂L/∂b = 2(wx+b−y)`
Update w and b by subtracting learning-rate times gradient.

## Runnable example
```python
import numpy as np
x = np.array([1., 2., 3.])
y = np.array([2., 4., 6.])
w, b, lr = 0.0, 0.0, 0.01
for epoch in range(1000):
    pred = w*x + b
    error = pred-y
    dw = 2*np.mean(error*x)
    db = 2*np.mean(error)
    w -= lr*dw
    b -= lr*db
print(w, b)  # approaches 2 and 0
```

## Evaluation metrics
Accuracy = correct predictions / total. Accuracy may mislead when classes are imbalanced. Also learn precision, recall, F1, confusion matrix, and ROC-AUC where suitable.

## Overfitting and underfitting
Underfitting: model too simple or insufficiently trained; poor on training and new data. Overfitting: learns noise or quirks of training examples; poor generalization. Remedies include representative data, simpler model, regularization, early stopping, and suitable augmentation.

## Bias and variance
High bias means the model cannot capture important patterns. High variance means performance changes strongly with training data. We want good generalization to new examples.

## Regularization
L2 regularization adds `λΣw²` to data loss. λ controls penalty; too much can underfit.

## Exercises
Give regression/classification examples; explain why test loss matters; describe overfitting; learning rate too high/low effects; why accuracy can mislead.

## Mini-project
Train linear regression on synthetic data, plot loss across epochs, vary learning rate, and compare curves.