## Neural Networks

Neural Networks can be formed by stacking several sigmoid units together

![alt text][logo1]

[logo1]: 1.png "1"

The calculation can be done by chaining the output of one sigmoid unit, to the input of the next sigmoid unit

## Neural Network Output

Repeated Logistic Regression across the multiple Neurons

![alt text][logo2]

[logo2]: 2.png "2"

## Vectorizing Across Multiple Training Examples

Training examples are stacked up horizontally in a matrix

The number of columns are the number of training examples

The number of rows are the number of hidden units

![alt text][logo3]

[logo3]: 3.png "3"

## Activation Functions

![alt text][logo4]

[logo4]: 4.png "4"

Sigmoid - Has non-zero mean. Only use this at output layer when you have binary classification `0` or `1`

TanH - Has zero mean. Use when the problem is a probability `0` to `1`

RelU -  `max(0,z)`. Use together with TanH

Leaky ReLU - `max(0.01*z,z)`

TanH is better than sigmoid is almost all cases:

1. Since data is centered around 0, the derivatives are higher
2. Avoids bias in the gradients

Use TanH for the hidden layers, use Sigmoid for the output function

One downside of TanH and Sigmoid: if `z` is very large or small, the slope of the function is close to zero. This will slow down learning

A solution to that is ReLU. This will allow the learning to be faster due to the steeper gradient when `z` is almost zero

Leaky RelU has a non-zero value when `z` is negative

## Why Non-Linear Activation Functions?

Hidden layers should never be linear functions

If your activation functions are linear, then no matter how many layers your put, you will just be computing a linear function

There is thus no point in adding hidden layers

Combinations of linear functions result in a linear function

Linear activation functions should only be used as the output layer, never in the hidden.

## Deravitives of Activation Functions

Back propagation with Gradient Descent requires calculating the derivative of the activation functions in each node

![alt text][logo5]

[logo5]: 5.png "5"

![alt text][logo6]

[logo6]: 6.png "6"

![alt text][logo7]

[logo7]: 7.png "7"
