# Train/ Dev/ Test set

Applied ML is a highly iterative process

1. no. layers
2. no. hidden units
3. learning rates
4. activation function

Splitting the data into training, dev and test set for building models

Sample ratio values are 70/15/15, but it is highly dependent on the amount of data you have

If you have millions of examples, it can be 99/1/1 ratio

Make sure your dev and test sets come from the same distribution

Not having a test set might be okay, but you must have a dev set for validation

This allows you to more efficiently evaluate bias and variance of your model

# Bias/ Variance

Look at your training set error, and your dev set error to tell your bias and variance

![alt text][logo1]

[logo1]: 1.png "1"

High Variance

```
Train Set Error: 1%

Dev Set Error: 11%
```

High Bias

```
Train Set Error: 15%

Dev Set Error: 16%
```

High Bias and High Variance

```
Train Set Error: 15%

Dev Set Error: 16%
```

Low Bias and Low Variance

```
Train Set Error: 0.5%

Dev Set Error: 1%
```

# Basic Recipe for Machine Learning

Tackling High Bias:

1. Bigger Network
2. Training it longer
3. Different NN architecture

Tackling High Variance:

1. More data
2. Regularization
3. Different NN architecture

In Neural Networks, there isn't really a bias-variance trade off, there are tools that work solely on bias and trade off
