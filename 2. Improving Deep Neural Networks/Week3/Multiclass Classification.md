# Softmax Regression

Generalization of logistic regression, which is binary classification, to a multiclass classification called softmax

The outputs of each class must sum to 1

The softmax activation function computes a temporary variable `t = e^(z)`

Activation `A` will be normalized over all the `t`

![alt text][logo2]

[logo2]: 2.png "2"

# Training a Softmax Classifier

Hardmax places a 1 to the predicted element, and 0 to the rest, while Softmax places probability values

Softmax: `[0.842, 0.042, 0.002, 0.114]`

Hardmax: `[1, 0, 0, 0]`

When number of classes = 2, Softmax generalizes to Logistic Regression (Binary classification)

Loss function for Softmax Classifier is the summation of `ylog(y')`

If `y'` is large, `log(y')` is small, thus minimizing the loss

Cost function for Softmax Classifier is the summation of all loss functions for each data point

# Gradient Descent with Softmax

Forward Propagation

`Z --> A --> y' --> L(y,y')`

Back Propagation

`dz = y' - y`


