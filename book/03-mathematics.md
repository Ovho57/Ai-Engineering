# 03 — Mathematics for AI (Readable Edition)

This chapter uses **plain-text, line-by-line equations** so they display clearly on phones, GitHub, and simple Markdown viewers. Read each line from top to bottom.

## 1. Numbers, variables, and equations

A **scalar** is a single number: 3, -2, or 0.5.

A **variable** is a symbol that represents a number. Example: x.

Example equation:

    2x + 3 = 11
    2x     = 11 - 3
    2x     = 8
    x      = 8 / 2
    x      = 4

AI models use variables for inputs, weights, biases, and outputs.

## 2. Functions

A function takes an input and produces an output.

    f(x) = 2x + 1

If x = 3:

    f(3) = 2(3) + 1
    f(3) = 6 + 1
    f(3) = 7

A neural network is a function: it receives data and produces a prediction.

## 3. Exponents and logarithms

Exponent:

    2^3 = 2 × 2 × 2 = 8

Logarithm reverses exponentiation:

    log₂(8) = 3

Because:

    2^3 = 8

Logs appear in probability, information theory, and loss functions.

## 4. Vectors

A **vector** is an ordered list of numbers.

    a = [1, 2]
    b = [3, 4]

Add matching positions:

    a + b = [1 + 3, 2 + 4]
          = [4, 6]

Multiply a vector by a scalar:

    3 × [2, 5] = [3 × 2, 3 × 5]
                = [6, 15]

Vectors can represent the features of one example.

## 5. Dot product (important for neurons)

Multiply matching values, then add the products.

    a = [2, 3]
    b = [4, 5]

    a · b = (2 × 4) + (3 × 5)
          = 8 + 15
          = 23

General form:

    a · b = a₁b₁ + a₂b₂ + ... + aₙbₙ

A neuron commonly calculates:

    weighted_sum = (input₁ × weight₁)
                 + (input₂ × weight₂)
                 + ...
                 + bias

Example:

    input  = [2, 3]
    weight = [4, 5]
    bias   = 1

    weighted_sum = (2 × 4) + (3 × 5) + 1
                 = 8 + 15 + 1
                 = 24

## 6. Matrices

A **matrix** is a rectangular grid of numbers.

    A = [ 1  2 ]
        [ 3  4 ]

This matrix has 2 rows and 2 columns. Its shape is:

    (2, 2)

### Matrix multiplication: shape rule

If A has shape (m, n), and B has shape (n, p), then:

    A × B has shape (m, p)

The **inside dimensions must match**.

    (2 × 3) × (3 × 1) -> (2 × 1)  VALID
    (2 × 3) × (2 × 1) ->          INVALID

### Worked example

    A = [ 1  2 ]
        [ 3  4 ]

    B = [ 5 ]
        [ 6 ]

First output:

    (1 × 5) + (2 × 6)
    = 5 + 12
    = 17

Second output:

    (3 × 5) + (4 × 6)
    = 15 + 24
    = 39

Therefore:

    A × B = [ 17 ]
            [ 39 ]

Matrix multiplication lets a computer calculate many neuron outputs efficiently.

## 7. Derivatives: measuring change

A derivative tells us how quickly a function changes at a point.

For:

    f(x) = x²

The derivative is:

    f'(x) = 2x

At x = 3:

    f'(3) = 2 × 3
          = 6

The slope at x = 3 is 6.

Useful rules:

    If f(x) = x², then f'(x) = 2x
    If f(x) = 3x, then f'(x) = 3
    If f(x) = constant, then f'(x) = 0

Training needs derivatives because they tell us how changing a parameter changes the loss.

## 8. Partial derivatives and gradients

A model may have many parameters, for example weight w and bias b.

    Loss = L(w, b)

A **partial derivative** measures how loss changes with one parameter while the others are held fixed:

    ∂L/∂w = change in loss with respect to w
    ∂L/∂b = change in loss with respect to b

The **gradient** collects all partial derivatives:

    gradient = [ ∂L/∂w, ∂L/∂b ]

Think of the gradient as an arrow pointing toward the direction of fastest increase in loss. To reduce loss, move in the opposite direction.

## 9. Chain rule (backpropagation depends on this)

If:

    y = f(g(x))

Then:

    dy/dx = f'(g(x)) × g'(x)

In words:

    derivative of the outside function
    multiplied by
    derivative of the inside function

Neural networks are functions stacked inside other functions. Backpropagation applies the chain rule backward through these layers to calculate parameter gradients.

## 10. Gradient descent

Gradient descent updates a parameter in the direction that reduces loss.

Readable update rule:

    new_weight = old_weight - (learning_rate × gradient)

Symbols:

    w_new = w_old - η × (∂L/∂w)

Here:
- w_old = current weight
- w_new = updated weight
- η (eta) = learning rate
- ∂L/∂w = gradient of loss with respect to the weight

Example:

    old_weight = 5
    learning_rate = 0.1
    gradient = 2

    new_weight = 5 - (0.1 × 2)
               = 5 - 0.2
               = 4.8

Example with a negative gradient:

    old_weight = 2
    learning_rate = 0.05
    gradient = -4

    new_weight = 2 - (0.05 × -4)
               = 2 - (-0.2)
               = 2 + 0.2
               = 2.2

A learning rate that is too large can overshoot. A very small learning rate can make training slow.

## 11. Probability

Probability is a number from 0 to 1.

    0   = impossible
    0.5 = 50% probability
    1   = certain

Convert probability to percentage:

    percentage = probability × 100

Example:

    0.8 × 100 = 80%

Important: a model's confidence score is not automatically a reliable real-world probability. Calibration and evaluation matter.

## 12. Mean, variance, and standard deviation

Values:

    [2, 4, 6]

Mean:

    mean = (2 + 4 + 6) / 3
         = 12 / 3
         = 4

Population variance:

    variance = ((2 - 4)² + (4 - 4)² + (6 - 4)²) / 3
             = (4 + 0 + 4) / 3
             = 8 / 3
             ≈ 2.67

Standard deviation:

    standard_deviation = square_root(variance)
                       ≈ square_root(2.67)
                       ≈ 1.63

Variance and standard deviation describe how spread out data is.

## 13. Shapes and dimensions: a must-know AI skill

Shape means the dimensions of a tensor or array.

Examples:

    [7]                 -> shape (1,) or one value
    [1, 2, 3]           -> shape (3,)
    [[1, 2], [3, 4]]    -> shape (2, 2)

For a batch of 32 examples, each with 10 features:

    shape = (32, 10)

Interpretation:

    32 = number of examples
    10 = features per example

Many beginner AI bugs are shape mismatches. Always inspect shapes when code fails.

## Practice (try before reading answers)

1. Calculate [3, 2] · [4, 7].
2. What is the output shape of (2 × 3) multiplied by (3 × 1)?
3. Find the derivative of f(x) = 3x².
4. Update w = 2 when learning rate = 0.05 and gradient = -4.
5. Calculate the mean of [5, 7, 9].
6. Explain the chain rule using your own words.
7. A batch has 64 examples and 12 features each. What is its shape?

### Answers

1. (3 × 4) + (2 × 7) = 12 + 14 = 26
2. (2 × 1)
3. f'(x) = 6x
4. w_new = 2 - (0.05 × -4) = 2.2
5. (5 + 7 + 9) / 3 = 7
6. Multiply the derivative of the outer function by the derivative of the inner function.
7. (64, 12)

## Mini-project

Use Python and NumPy to:
1. Create two vectors.
2. Add them.
3. Calculate their dot product.
4. Create two matrices and multiply them.
5. Print every array's shape.

Do not only copy the code. Predict each result first, then run it and compare.
