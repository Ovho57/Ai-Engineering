# 10 — AI Model Engineering

Model engineering is the work that makes experiments reliable, reproducible, usable, and maintainable.

## Reproducibility
Record:
- dataset source and version,
- preprocessing steps,
- model architecture,
- hyperparameters,
- random seeds where possible,
- software versions,
- training duration and hardware,
- evaluation results.

A random seed can make some operations repeatable, but exact reproducibility may still vary across hardware and library versions.

## Checkpoints
Save model checkpoints during training. They help recover from interruptions and compare experiments. Save optimizer state when continuing training.

## Experiment tracking
Use a table or tracking tool to record each run: model, learning rate, batch size, epochs, validation metric, and notes. Change a small number of variables at a time.

## Hyperparameters
Parameters are learned from data (weights and biases). **Hyperparameters** are choices made by the engineer, such as learning rate, batch size, number of layers, and regularization strength.

## Training stability
Watch for:
- loss becoming NaN or infinite,
- exploding gradients,
- gradients becoming very small,
- incorrect tensor shapes,
- data leakage,
- learning rate too high,
- input scales or labels being wrong.

Gradient clipping can limit gradient magnitude in some settings. It is not a substitute for diagnosing the underlying issue.

## Evaluation
Evaluate on data matching intended use. Inspect more than one metric. Review examples the model gets wrong. Compare against a simple baseline. Consider fairness, privacy, robustness, and failure cost.

## Deployment concepts
A model can be exposed through a local program, API, or service. A deployment needs:
- input validation,
- preprocessing consistent with training,
- model loading,
- output handling,
- logging that protects private data,
- versioning,
- monitoring,
- rollback plan.

## Inference vs training
Training calculates gradients and updates parameters. Inference uses a trained model to produce predictions; it usually does not update weights. Inference may still be computationally expensive.

## Efficiency
Common strategies include smaller models, batching, quantization, caching, efficient data loading, and GPU use. Every optimization should be measured for quality and latency.

## Model limitations and safety
Document intended use, known limitations, evaluation scope, and situations where the model should not be trusted. Keep human oversight for consequential decisions. Protect data and credentials.

## Exercises
Distinguish parameters from hyperparameters; why save optimizer state?; why compare a baseline?; explain inference; list a deployment failure mode.

## Project
Package a trained small model into a command-line predictor. Include preprocessing, model version, a README, test cases, and a limitations section.