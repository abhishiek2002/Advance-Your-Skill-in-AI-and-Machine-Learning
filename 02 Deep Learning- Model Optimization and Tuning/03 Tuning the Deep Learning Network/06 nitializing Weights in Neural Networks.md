# Initializing Weights in Neural Networks

## Overview

Initializing weights and biases is a crucial step when building a neural network model. Proper initialization helps speed up learning and improves the final accuracy achieved by the network.

### Importance of Weight Initialization

* **Speed of Learning:** Good initialization leads to faster convergence during training.
* **Final Accuracy:** Proper initialization can result in better model performance.
* **Gradient Descent Efficiency:** Initial values influence how gradients propagate through the network.

## Common Initialization Techniques

1. **Random Normal Initialization**

   * Draws weights from a standard normal distribution (mean=0, std=1).
   * Most commonly used and works well for most use cases.

2. **Zeros Initialization**

   * All weights initialized to 0.
   * Generally leads to poor performance, as gradients for all nodes are the same initially, causing slow or stalled learning.

3. **Ones Initialization**

   * All weights initialized to 1.
   * Similar drawbacks as zeros; all nodes start with the same value.

4. **Random Uniform Initialization**

   * Draws weights from a uniform distribution.
   * Values are evenly spread across a range.
   * Performs well for many use cases.

### Difference Between Normal and Uniform Distributions

* **Normal Distribution:** Values are clustered around the mean, with fewer extreme values.
* **Uniform Distribution:** Values are evenly spread out across the specified range.

### Advanced Techniques

* Custom initializers can be defined for specialized use cases.
* Deep learning libraries often provide more advanced initializers (e.g., Xavier, He initialization) for better convergence.

## Experiment

* **Setup:** Keep the base model settings constant and vary only the weight initialization technique.
* **Observations:**

  * Random normal and random uniform produce good performance.
  * Ones and zeros perform poorly, as expected.

### Conclusion

* Always prefer random initialization methods (normal or uniform) for most use cases.
* Avoid using all zeros or ones unless there's a specific reason.
* Experimenting with initialization can help fine-tune model performance.
