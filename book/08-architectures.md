# 08 — Neural Network Architectures

An architecture is the arrangement of layers and operations in a model. Different architectures are useful for different kinds of data and tasks.

## Multilayer perceptron (MLP)
An MLP is made of dense/fully connected layers and nonlinear activations. It is a good starting architecture for tabular features and simple problems. Dense layers connect each input unit to each output unit.

## Convolutional neural networks (CNNs)
CNNs are especially useful for images. A convolutional filter scans local regions and detects patterns such as edges, textures, and shapes.

Key concepts:
- **Kernel/filter:** small learned matrix applied across image positions.
- **Stride:** distance the filter moves each step.
- **Padding:** added border values that affect output size.
- **Channels:** feature maps or image color channels.
- **Pooling:** reduces spatial dimensions, e.g. max pooling.

Early layers may detect simple patterns; deeper layers can combine them into more complex features. This is an intuition, not a guarantee about every trained network.

## Recurrent neural networks (RNNs)
RNNs process sequences step by step and carry a hidden state. They were used for language and time series. Long sequences can make gradients vanish or explode.

## LSTM and GRU
LSTM and GRU introduce gating mechanisms to help manage information over time. They can handle some long-range sequence dependencies better than simple RNNs, although transformers are often preferred in modern large-scale language systems.

## Attention
Attention lets a representation selectively combine information from other positions. A query asks what information is relevant; keys describe candidate items; values contain information to combine.

Scaled dot-product attention:

`Attention(Q,K,V) = softmax(QKᵀ / √dₖ) V`

Q, K, and V are query, key, and value matrices. `dₖ` is key dimension. Scaling helps keep dot products in a useful range.

## Transformers
A transformer commonly combines:
- token embeddings,
- positional information,
- multi-head attention,
- feed-forward blocks,
- residual connections,
- normalization.

Transformers can process relationships across sequence positions and scale effectively with data and compute.

## Autoencoders
An autoencoder learns to encode input into a smaller or structured representation and decode it back. It is trained to reconstruct input. It can support representation learning and compression, but reconstruction does not automatically mean useful compression.

## Generative models
Generative models learn patterns in data and produce new samples. Families include autoregressive models, variational autoencoders, and diffusion models. Each has different objectives and sampling processes.

## Architecture choice
Choose based on data, task, compute, latency, and evaluation—not because a model is trendy. A small well-designed model may outperform a huge model on a narrow dataset.

## Exercises
Compare MLP and CNN; explain filter and stride; why do RNNs carry state?; explain attention with a metaphor; list common transformer components.

## Project
Build an image classifier using a small CNN on a public beginner dataset. Compare it with an MLP and discuss errors.