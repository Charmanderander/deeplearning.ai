# Normalizing Activations in a Network

We learnt previously to normalize inputs to a network

Now we can normalize the Activations in the networks to make the training faster

Traditionally, you would use the inputs to each neuron to compute `Z`, and pass `Z` through a sigmoid function to get an activation `A`

Now, instead of `Z` passing into the activation functions use `Z'`, which is calculated by

`Znorm = Z - u / (sig ^ 2 + e) ^ 0.5`

`Z' = G * Znorm + B`, where gamma `G` and beta `B` are parameters to be learnt

![alt text][logo1]

[logo1]: 1.png "1"

# Fitting Batch norm into a Neural Network

The parameters will now be weights `W`, bias `b`, beta `B` and gamma `G`

Batch norm removes the bias `b` during the normalization step, leaving you with `W`, `B` and `G`

# Why does Batch Norm work?

By normalizing values, you can speed up learing by narrowing the range of values, just like normalizing input values

It makes the weights deeper in your network (layer 10) more robust to changes compared to weights in the earlier part (layer 1)

**Covariate Shift** means there is a shift in distribution from the learning data to the testing data.

Given learned mapping of `X --> Y`, if `X` changes, you need to retrain the model.

Batch Norm reduces the amount of shifting done by the weights, and this reduces covariate shifting as well. Thus it can make the weights more stable to changing weights

The weights across different layers are constrained to have the same mean and variance

Batch norm also have a small regularization effect

Each mini batch has it's mean and variance computed only from that mini batch. This adds some noise to the mini batch, contributing to the regularization effect

Bigger mini batch size = smaller regularization effect from Batch norm.

But dont use batch norm for regularization! That's only an unintended side effect.

# Batch norm at test time

Batch norm process your data one mini batch at a time during training, but at test time, you may need to process the examples one at a time

Batch  norm requires you to find mean and variance. But if you're processing test data one example at a time, it doesnt make sense to have a mean and variance.

We hence estimate the mean and variance using exponentially weighted averages across mini batches

Each mini batch will have different values of mean and variance across the different layers. During test time, we just make use of those values obtained during training to calculate `Znorm`

We calculate a single value of mean and variance using exponentially weight moving average across all mini batches.
