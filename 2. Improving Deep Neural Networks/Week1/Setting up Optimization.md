# Normalizing inputs

1. Subtract the mean (zeroing the data)
2. Normalize the variance

![alt text][logo4]

[logo4]: 4.png "4"

Scale your test and training data in the same way

Unormalized inputs tend to look like a bowel that is elongated, and find the minima can be difficult

![alt text][logo5]

[logo5]: 5.png "5"

# Vanishing and Exploding Gradients

When training a deep network, your derivaties can get either too big or too small

If the weights are just slightly larger than 1, a big network can explode the gradient

If the weights are just slightly smaller than 1, a big network can diminish the gradient

# Weight Initilization for Deep Neural Networks

Different weight initialization should be used for different activation functions.

This prevents the weights from exploding too quickly, or decaying to 0 too quickly

# Numerical Approximation of Gradients

Taking a two sided difference to numerically verify that it is a correct implementation of the derivative

# Gradient Checking

For each layer, add get the (theta + epsilon) and (theta - epsilon), which will approximate the gradient of `J` to theta

# Tips for gradient checking

Dont use grad check in training, only in debug

If your algo fails grad check, find the bug

Remember to use regularization

Doesnt work with drop-out

Run at random initialization after some training
