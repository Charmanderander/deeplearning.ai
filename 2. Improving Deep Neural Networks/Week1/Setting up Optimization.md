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



