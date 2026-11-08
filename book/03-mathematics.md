# 03 — Mathematics for AI

Math describes the calculations inside models. Learn meanings and practice, not just memorized formulas.

## Scalars, variables, equations
A scalar is one number (e.g. 3 or -0.2). Solve `2x + 3 = 11`: subtract 3, giving `2x=8`; divide by 2, so `x=4`. Weights and biases are often scalar parameters.

## Functions
A function maps input to output. For `f(x)=2x+1`, `f(3)=7`. A model is a function mapping input data to predictions.

## Exponents and logarithms
`2³ = 2×2×2 = 8`. A logarithm reverses exponentiation: `log₂(8)=3`. Logs appear in probability and loss functions.

## Vectors
A vector is an ordered list: x = [2,4,6]. Vector addition adds matching components: [1,2]+[3,4]=[4,6]. Scalar multiplication: 3[2,5]=[6,15]. Features for one example can form a vector.

## Dot product
For vectors of equal length: `x·w = x₁w₁ + ... + xₙwₙ`. Example [2,3]·[4,5] = 2×4+3×5=23. A neuron commonly computes a dot product plus bias.

## Matrices
A matrix is a rectangle of numbers. A 2-row, 3-column matrix has shape 2×3. Multiplication rule: (m×n)(n×p) produces (m×p); inner dimensions must match.

Example: [[1,2],[3,4]] × [[5],[6]] = [[17],[39]]. Each output is a row dot product. Matrix operations compute many neurons efficiently.

## Derivatives
A derivative measures local change. If `f(x)=x²`, then `f'(x)=2x`; at x=3 the slope is 6. Training needs derivatives to know how parameters affect loss.

## Partial derivatives and gradients
For loss L(w,b), `∂L/∂w` describes the change with w while holding b fixed. The gradient collects derivatives: ∇L = [∂L/∂w, ∂L/∂b]. It points toward steepest increase; minimizing loss moves opposite it.

## Chain rule
For y=f(g(x)): `dy/dx = f'(g(x)) × g'(x)`. Neural networks compose many functions. Backpropagation applies the chain rule efficiently through layers.

## Gradient descent
`w_new = w_old − η(∂L/∂w)`. Here η is learning rate. If w=5, gradient=2, η=0.1, then w_new=4.8. A huge learning rate may overshoot; a tiny one may learn slowly.

## Probability and statistics
Probability ranges from 0 (impossible) to 1 (certain). Mean: `x̄ = (sum of values)/n`. Population variance: `σ² = sum((x−mean)²)/n`; standard deviation is its square root. Statistics describe data spread and uncertainty. Model confidence is not necessarily a calibrated real-world probability.

## Practice
1. Dot product [3,2]·[4,7].
2. What shape results from (2×3) times (3×1)?
3. Derivative of 3x².
4. Update w=2 with gradient −4 and η=0.05.
5. Explain chain rule in your own words.

## Mini-project
Use NumPy to implement vector addition, dot product, and matrix multiplication. Check results manually.