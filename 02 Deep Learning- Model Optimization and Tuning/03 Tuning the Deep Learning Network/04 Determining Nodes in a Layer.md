# Determining Nodes in a Layer

## Overview

In this section, we explore how the number of nodes in a hidden layer affects the performance of a neural network model. Nodes in a layer represent perceptrons, each with weights and biases, which together capture learning from training data.

## Key Concepts

* Increasing the number of nodes allows the model to learn more complex relationships.
* Higher node counts result in increased training and inference time.
* More nodes can also increase the risk of overfitting.
* Generally, the number of nodes should be between the input layer nodes (number of features) and output layer nodes (number of classes).
* Start with a small number (e.g., 32) and increase based on experimentation.

## Experiment Setup

* Dataset: Iris dataset (preprocessed and loaded using the `get_data` method).
* Base Model: Two hidden layers.
* Node Counts Tested: 8, 16, 24, 32.
* Other parameters: Use defaults from the base model configuration.

## Procedure

1. Load the training data using `get_data`.
2. Set up the model with two hidden layers.
3. Vary the number of nodes in each hidden layer from 8 to 32 in steps of 8.
4. Build and train the model for each node configuration.
5. Capture accuracy after each epoch.
6. Review model summary to observe the number of parameters and resource usage.
7. Plot the results to compare performance across different node counts.

## Observations

* As the number of nodes increases, the number of parameters grows, resulting in larger models.
* Accuracy generally improves with more nodes as the model can capture more patterns.
* For this use case, 16 nodes per layer provided the best accuracy.
* Small datasets may lead to inconsistent results; larger datasets are recommended for real-life scenarios.

## Recommendation

* Start with a low node count (e.g., 16 or 32) and tune upwards based on observed performance.
* Monitor resource usage to avoid unnecessarily large models.
* Validate results on sufficiently large and balanced datasets to ensure consistent outcomes.
