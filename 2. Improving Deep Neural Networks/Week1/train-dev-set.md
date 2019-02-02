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
