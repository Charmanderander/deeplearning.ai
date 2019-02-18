# Optimization Algorithms

# Mini Batch Gradient Descent

Training on large dataset is slow, so we break them down into batches (or mini-batches)

Split up the training set into mini batches and train the model based over each mini-batch

For each mini-batch, do forward propagation and back propagation (for each example in the mini-batch)

An Epoch is the number of times you run the entire dataset through the model (forward/back propagation)

# Understanding Gradient Descent

With Batch gradient descent, cost decreases per iteration

With mini-batch gradient descent, some batches may be harder to train on, and some batches may be easier to train on. Hence, we won't get a smooth curve downwards, but a fluctuating curve

![alt text][logo1]

[logo1]: 1.png "1"

# Choosing mini batch size

Size of data set - `M`

If mini batch = `M`, you get Batch Gradient Descent

If mini batch size = 1, you get Stochastic Gradient Descent (Every example is a batch)

Stochastic Gradient Descent is very noisy, and can lead you to a wrong direction.

Stochastic Gradient Descent will never converge, but loitering around the minimum. It loses speed up from vectorization.

mini batch size should be > 1 and < `M`

If training set is small, use Batch Gradient Descent (<2000)

If training set is large, use `M` = 64, 128 or 512 (power of 2)


