# Regularization

Regularization tackles the problem of high variance (Difference in train and validation results)

We regularize the weights, and omit regularizing the bias `b`. Regularizing the bias `b` wont make much of a difference, because it has low dimentionality

![alt text][logo2]

[logo2]: 2.png "2"

L2 Regularization: taking the euclidean normals (used more often)

L1 Regularization: `w` ends up being sparse and has a lot of zeros

L2 Regularization adds a penalty to the cost function. The penalty value is calculated by summing the square of all the weights

![alt text][logo3]

[logo3]: 3.png "3"

# Why does Regularization prevent overfitting?

The penalty introduced by the regularization sets `w` closer to zero, or reducing the impact of the weights. This makes the model less complicated, and its more simple or smaller, which makes it less prone to overfitting

# Dropout Regularization

During the training phase, occasionally ignore some neurons.

At each iteration, randomize the probability to choose some neurons in the hidden layer to set their inputs to zero

Inverted Dropout technique: ensures that the expected value remains the same

# Understanding Dropout

In training a neural network, you can't rely solely on one feature, which may dominate (and thus overfit) the network. Dropout occasionally forgets that feature, and spreads the weight out to include other non-dominant but important features.

Dropout is almost the same as L2 regularization

You can specify the amount of dropouts for each layer (does not have to be a fixed value)

Downside for dropout: Cost function is less well defined because you're randomly killing off nodes

# Other Regularization Techniques

- For images, you can flip, skew, crop, and rotate pictures to add to your training set

- Use early stopping to stop the training iterations when your training and testing score starts to diverge. Early stopping prevents your model from growing too lage, and thus become prone to overfitting

- Try using just L2, and not early stopping first
