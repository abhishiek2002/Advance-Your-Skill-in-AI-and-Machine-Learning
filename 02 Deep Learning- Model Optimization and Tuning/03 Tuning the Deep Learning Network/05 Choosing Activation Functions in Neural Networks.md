# Choosing Activation Functions in Neural Networks

## Overview

Activation functions are critical in determining the performance and stability of a neural network. They are used in both hidden and output layers, but the selection criteria for each differs. This section explains how to choose activation functions, their effects on the network, and demonstrates an experiment to compare them.

## Hidden Layer Activation Functions

* The choice of activation function in hidden layers depends on the problem type and network architecture.
* Activation functions influence:

  * Gradient descent stability
  * Training speed
  * Non-linear transformation capability

### Common Choices:

* **ReLU (Rectified Linear Unit)**

  * Works well for standard feed-forward networks and convolutional neural networks (CNNs).
  * Efficient computation and reduces vanishing gradient issues.
* **Sigmoid**

  * Suitable for Recurrent Neural Networks (RNNs).
  * Can suffer from vanishing gradients for deep networks.
* **Tanh**

  * Similar to sigmoid but outputs values between -1 and 1.
  * Often performs better than sigmoid for hidden layers.

> Default recommendation: Start with ReLU and experiment for your specific use case.

## Output Layer Activation Functions

The activation function for the output layer is determined by the type of problem:

* **Binary Classification:** Sigmoid (outputs probability between 0 and 1)
* **Multi-Class Classification:** Softmax (outputs probability distribution across classes)
* **Regression:** Linear activation (outputs continuous values)

## Experiment: Hidden Layer Activation Function Comparison

**Objective:** Determine which hidden layer activation function yields the best accuracy.

### Setup:

* Activation functions tested: ReLU, Sigmoid, Tanh
* Other hyperparameters kept at default values.
* Dataset: Iris classification problem
* Number of layers and nodes: Default from previous experiment (2 layers, 16 nodes each)

### Observations:

* ReLU and Tanh provided similar accuracy results.
* Sigmoid underperformed for this specific dataset and network architecture.
* Changing activation functions does not affect the number of parameters in the network but influences the activations and training dynamics.

### Recommendation:

* Use **ReLU** as a starting point for hidden layers.
* Tanh can be considered as an alternative.
* Sigmoid should generally be reserved for output layers in binary classification tasks.
* Always experiment and validate performance on your specific dataset.
