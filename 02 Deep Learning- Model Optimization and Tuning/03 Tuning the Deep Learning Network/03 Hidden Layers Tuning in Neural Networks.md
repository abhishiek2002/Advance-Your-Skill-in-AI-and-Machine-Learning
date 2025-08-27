### Hidden Layers Tuning in Neural Networks

**Overview:**
This section focuses on tuning the number of hidden layers in a neural network. Hidden layers are crucial components that allow the network to learn complex relationships between input features and target variables. However, increasing layers can also raise training cost, inference time, and risk of overfitting.

**Key Points:**

* Hidden layers learn from training data to improve model performance.
* More layers allow learning of more complex relationships.
* Increasing layers increases computational cost and memory usage.
* Risk of overfitting grows with more layers.
* For simple problems, 2 hidden layers are often sufficient.
* Additional layers should be added only if the desired accuracy is not achieved.

**Experiment Setup:**

* Base model: same as previous experiments.
* Hidden layer count: varied from 1 to 5.
* Each hidden layer: 32 nodes.
* Other hyperparameters: kept constant.
* Dataset: Iris dataset from common experiment functions.

**Procedure:**

1. Retrieve the base model configuration and training data.
2. Modify only the number of hidden layers in the model.
3. Create the model for each hidden layer count.
4. Train the model and record accuracy per epoch.
5. Plot the accuracy trends for comparison.

**Observations:**

* 1 hidden layer: accuracy starts low but gradually improves.
* 2 hidden layers: achieves high accuracy quickly, optimal for this use case.
* 3 or more hidden layers: accuracy drops, indicating overfitting or excessive model complexity.
* Number of parameters increases with layers, consuming more resources.

**Conclusion:**

* For this dataset and problem, 2 hidden layers provide the best balance between performance and resource usage.
* Avoid unnecessarily increasing hidden layers without experimental justification.

**Recommendation:**

* Use experimentation to determine optimal hidden layers for different datasets.
* Monitor resource usage and overfitting as layers increase.
* Fix optimal layer count before moving on to tuning other hyperparameters.
