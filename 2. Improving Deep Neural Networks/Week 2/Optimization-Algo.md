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

# Gradient Descent with Momentum

You want slower learning on because you don't want oscillations in gradient descent, but you also don't want learning to be too slow

On iteration `T`, compute derivatives as per usual for `dW` and `dB`. Modify it with the moving average computation:

`VdW = Z * VdW + (1 - Z) * dW`

`VdB = Z * VdB + (1 - Z) * dB`

This smooths out gradient descent, so osciallations dont happen so frequently

![alt text][logo2]

[logo2]: 2.png "2"

# RMSprop

Root Mean Square Propagation to speed up Gradient Descent

On iteration `T`, compute derivatives as per usual for `dW` and `dB`. Modify it with the moving average computation:

`SdW = S * dW + (1 - S) * dW^2`

`SdB = S * dB + (1 - S) * dB^2`

The difference is in the squared

The weights and bias are updated the same way, but the difference is divided by the square-root of `SdW` and `SdB`

![alt text][logo3]

[logo3]: 3.png "3"

# Adam Optimization (Adaptive Moving)

Gradient Descent with Momentum + RMSprop = Adam!

![alt text][logo4]

[logo4]: 4.png "4"

# Learning Rate Decay

We want to reduce learning rate because as the approach the minimum, we don't want that much oscillations

![alt text][logo5]

[logo5]: 5.png "5"

Slowly reduce learning rate over time

1 epoch = 1 pass through the data

`Learning Rate (A) = A / (1 + Decay Rate * Epoch Num)`

As the epoch progresses, the learning rate `A` decreases

Other learning rates are Exponential Decay

`A = 0.95 ^ (epoch num) * A`

Or

`A = (A * K) / (epoch num)`

# Problem of Local Optima and Saddle Points

![alt text][logo6]

[logo6]: 6.png "6"

You are much more likely to run into a saddle point as opposed to a local optima in problems with high dimensions

In high dimension, to meet a local optima, all dimensions need to be either concave or convex, which is a very low probability

Instead, some dimensions may be concave, and some dimensions may be convex, leading to a saddle point

Plateaus can lead to a problem as well. Plateus are regions where the gradient are very close to zero

![alt text][logo7]

[logo7]: 7.png "7"
