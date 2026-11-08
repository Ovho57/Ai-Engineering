# 12 — Glossary and Formula Reference

## Glossary
- **AI:** systems performing tasks associated with intelligent behavior.
- **Algorithm:** defined steps for solving a problem.
- **Dataset:** collection of examples.
- **Feature:** input variable used by a model.
- **Label/target:** desired output for supervised learning.
- **Model:** parameterized function learned from data.
- **Parameter:** value such as weight or bias learned during training.
- **Hyperparameter:** engineer-selected setting such as learning rate.
- **Neuron:** unit computing weighted input, bias, and activation.
- **Weight:** learned coefficient controlling influence of an input.
- **Bias:** learned offset.
- **Activation:** function applied to a neuron's weighted sum.
- **Layer:** group of transformations in a network.
- **Forward pass:** compute predictions from input.
- **Loss:** scalar measure of prediction error/objective.
- **Gradient:** collection of derivatives of a function.
- **Backpropagation:** efficient computation of neural-network gradients.
- **Optimizer:** method that updates model parameters.
- **Epoch:** one pass through training data.
- **Batch:** examples processed together.
- **Learning rate:** scale of parameter update.
- **Overfitting:** fitting training-specific details that hurt generalization.
- **Underfitting:** failing to capture important patterns.
- **Inference:** using a trained model to predict.
- **Embedding:** learned vector representation.
- **Token:** unit produced by a tokenizer.
- **Transformer:** neural architecture based on attention and related blocks.

## Formula reference

### Neuron
`z = Σᵢ wᵢxᵢ + b`

### ReLU
`ReLU(z) = max(0,z)`

### Sigmoid
`σ(z) = 1/(1+e^(−z))`

### Softmax
`softmax(zᵢ) = exp(zᵢ)/Σⱼ exp(zⱼ)`

### Mean squared error
`MSE = (1/N)Σᵢ(ŷᵢ−yᵢ)²`

### Gradient descent
`θ ← θ − η∇L(θ)`

### Standardization
`z = (x−μ)/σ`

### Dot product
`x·w = Σᵢxᵢwᵢ`

### Matrix shape rule
`(m×n)(n×p) → (m×p)`

### Scaled dot-product attention
`Attention(Q,K,V) = softmax(QKᵀ/√dₖ)V`

## Symbols
- `x`: input
- `y`: target
- `ŷ`: prediction
- `w`, `W`: weight(s)
- `b`: bias
- `L`: loss
- `η`: learning rate
- `∇`: gradient
- `N`: number of examples
- `μ`: mean
- `σ`: standard deviation (or sigmoid function depending on context)
- `φ`: activation function

## Final advice
Return to this glossary whenever a symbol or term becomes confusing. Understanding grows through repeated use.