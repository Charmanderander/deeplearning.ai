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
