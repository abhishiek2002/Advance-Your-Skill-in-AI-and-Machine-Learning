## Optimizer Experiment

* **Objective:** Compare the performance of various optimizers for the Iris dataset example.

### Setup

* A list of optimizers is defined: `'sgd'`, `'rmsprop'`, `'adam'`, and `'adagrad'`.
* For each optimizer, the same model architecture is used; only the optimizer varies.
* A helper function `get_optimizer` (from the common experiment functions notebook) is used to set up the optimizer based on the selected option. It also accepts a `learning_rate` parameter.
* The model is compiled with the specified optimizer and trained.

### Observations

* The model structure does not change with different optimizers; only the parameter updates during training differ.
* Running the experiment and plotting the results showed that:

  * `sgd`, `rmsprop`, and `adam` performed reasonably well.
  * `adagrad` lagged behind in terms of early accuracy.
* Recommendation: Experiment with different optimizers and choose the one best suited for your specific dataset and use case.

### Next Steps

* Explore the impact of learning rate on optimizer performance (covered in the next video).
