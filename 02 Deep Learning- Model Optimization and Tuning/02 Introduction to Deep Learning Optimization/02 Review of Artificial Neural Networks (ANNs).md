# Review of Artificial Neural Networks (ANNs)

## Overview

Artificial Neural Networks (ANNs) are computational models inspired by the human brain. They consist of interconnected perceptrons (nodes) that process inputs and produce outputs. ANNs are used extensively in deep learning for tasks such as classification, regression, image recognition, and natural language processing.

## Structure of an ANN

* **Node (Perceptron):** The basic unit of an ANN, analogous to a human brain cell.
* **Layers:** Nodes are organized in multiple layers:

  * **Input Layer:** Receives independent variables. One node per variable.
  * **Hidden Layers:** Perform computations; can have multiple layers and nodes.
  * **Output Layer:** Produces the final predictions; number of nodes depends on prediction type.

### Example Architecture

* Input Layer: 3 nodes (representing 3 independent variables)
* Hidden Layer 1: 4 nodes
* Hidden Layer 2: 5 nodes
* Hidden Layer 3: 3 nodes
* Output Layer: 2 nodes

The number of layers and nodes is determined experimentally and may vary for different problems.

## Working of ANN for Predictions

1. Inputs are pre-processed and sent to the network.
2. Each node applies a formula on the input using its **weights**, **bias**, and **activation function**.
3. Outputs from a layer are passed to the next layer.
4. The process repeats until reaching the output layer, which produces the final predictions.

## Key Points

* Nodes within a layer are typically not connected to each other.
* Deep neural networks usually have 3 or more layers.
* Each node contains:

  * **Weights:** Influence the importance of input signals.
  * **Bias:** Helps the model fit data better.
  * **Activation Function:** Introduces non-linearity to capture complex patterns.

## Recommendation

It is recommended to watch introductory courses on deep learning, such as "Deep Learning Getting Started," to understand these concepts in greater depth.
