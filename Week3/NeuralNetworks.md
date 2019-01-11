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

## Other Activation Functions Other Than Sigmoid

Sigmoid - Has non-zero mean. Use when you have binary classification `0` or `1`

TanH - Has zero mean. Use when the problem is a probability `0` to `1`

RelU
