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

# Other Optimization Algorithms Other Than Gradient Descent

Exponentially Weight Averages

```
V0 = 0
V1 = 0.9 * V0 + 0.1 * X1
V2 = 0.9 * V1 + 0.1 * X2
...
VT = 0.9 * V(T-1) + 0.1 * XT
```

Or More generally

`VT = Z * V(T-1) + (1 - Z) * XT`

`VT` is approximately averaging over `1 / (1 - Z)` data points

A higher value of `Z` will result in a graph that reacts more slowly to changes, because it averages over a larger number of data points, and a smaller weight `1 - Z` is given to the current data.

# Bias Correction in Exponentially Weighted Averages

When you initialize `V0 = 0`, `V1 = 0.9 * V0 + 0.1 * X1` becomes very small, and is not a good estimate of the actual data, because the equation just becomes `V1 = 0.1 * X1`, which is wrong.

We need to add a bias correction, which is `V1 / (1 - Z^1)`, or more generally, `VT / (1 - Z^T)`. Because `Z < 1`, as `T` becomes large, `Z^T` approaches zero, which removes the bias correction (which is what we want)

