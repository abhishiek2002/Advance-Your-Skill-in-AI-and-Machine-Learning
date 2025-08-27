## Vanishing and Exploding Gradients

### Concept Overview

Building stable and accurate deep learning models relies on smooth progress during backpropagation. Backpropagation adjusts weights and biases in the network based on the computed errors from forward propagation.

### Gradient Descent Process

1. **Forward Propagation**: Compute predictions and error between estimated and actual target values.
2. **Backward Propagation**:

   * Compute delta values for the output layer.
   * Update the weights and biases for each layer based on delta values.
   * Propagate the deltas back through each layer until the first hidden layer.

### Problems During Backpropagation

* **Vanishing Gradients**:

  * Occurs when delta values are too small.
  * Subsequent forward propagation results in negligible weight updates.
  * Gradient descent stalls, leading to very slow or no learning.
  * Represented by a decay line in graphs, failing to approach the target.

* **Exploding Gradients**:

  * Occurs when delta values are too large.
  * Causes large fluctuations in weight updates.
  * Gradient descent oscillates and fails to converge.
  * Graphically represented by oscillations around the target line without convergence.

### Graph Illustration

* **Light Green Line**: Target values.
* **Blue Line**: Ideal gradient descent (stable convergence).
* **Yellow Line**: Vanishing gradients (stalls).
* **Dark Green Line**: Exploding gradients (oscillates).

### Mitigation Strategies

1. **Weight Initialization**: Start with optimal values to stabilize gradients.
2. **Activation Functions**: Experiment to find functions that maintain gradient stability.
3. **Batch Normalization**: Normalize outputs to reduce internal covariate shift and stabilize training.

**Note**: Monitoring gradients and applying proper techniques is critical to ensure efficient training of deep networks.
