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

## Gradient Descent in Neural Networks

![alt text][logo8]

[logo8]: 8.png "8"

After calculating forward propagation, you get `A[2]`, which is the output of the model. You use the loss function (by finding the difference between your model's output, and the actual output) to compute `d(A[2])`, which is `(-y/a) + (1-y)/(1-a)`.

Using `d(A[2])` and derivative chain rule, we calculate `d(z[2])`, which turns out to be simply `A[2] - y`

Using `d(z[2])`, you can then calculate the derivatives of the previous layers, and update their weights `w` and `b` accordingly.

We keep repeating this until `w` and `b` converges.

![alt text][logo9]

[logo9]: 9.png "9"

`A[2]` is the output of your model

`y` is the true values

`A[1]` is the output of the first hidden layer

`m` is your total training examples

## Random Weights Initialization

In Neural Networks, you cannot set your initial weights to 0, if not Gradient Descent will not work

The random values should be really small. This is because if the activation functions have too large `z`, the learning will be slow
