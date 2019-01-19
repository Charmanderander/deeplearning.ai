## Deep Layer Neural Networks

![alt text][logo1]

[logo1]: 1.png "1"

"Deep" just means the number of layers, as opposed to shallow

How deep a neural network goes is trail and error using cross validation

## Forward Propagation in Deep Layer NN

![alt text][logo2]

[logo2]: 2.png "2"

Inputs to each layers are the outputs of the previous layer

## Matrix Dimensions

`W[1] = (n[1], n[0])`

`W[2] = (n[2], n[1])`

`W[i] = (n[i], n[i-1])`

## Deep Representation

Earlier layers represent simple features of the inputs. Going down the network, we can combine these features to get a more complex representation

![alt text][logo3]

[logo3]: 3.png "3"

This applies to other data as well, instead of just images such as Audio

There mathematical functions that are much easier to compute using deep neural networks

## Building Blocks of a Deep NN

Forward and Backward propagation

![alt text][logo4]

[logo4]: 4.png "4"

## Forward and Backward Propagation

![alt text][logo5]

[logo5]: 5.png "5"

![alt text][logo6]

[logo6]: 6.png "6"

## Hyperparameters and Parameters

Parameters: The input data, weights, bias values

Hyperparameters: Learning rate, iterations, number of hidden layers, number of hidden unit, choice of activation function
