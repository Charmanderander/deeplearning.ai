## Logistic Regression as a Neural Network

Output label Y is either 0 or 1 (Binary classification)

![alt text][logo3]

[logo3]: 3.png "3"


When we implement Logistic Regression, we are trying to learn parameters `w` and `b` so that `y` is an accurate prediciton between 0 and 1

## Logistic Regression cost function

Loss Function Squared Error will not work well with Logistic Regression

![alt text][logo4]

[logo4]: 4.png "4"

If the true value of `y=1`, we want to push the value of `y-hat` to be large (since it's a sigmoid, the largest value is 1)

If the true value of `y=0`, we want to push the value of `y-hat` to be small (since it's a sigmoid, the largest value is 0)

The Cost Function is the average of the Loss Function applied to each example

Loss Function is applied to a single training example, while the Cost Function is the avrage across all training examples.

![alt text][logo5]

[logo5]: 5.png "5"

During training, we want to minimize the Cost Function

The Cost Function tells you how well your model did.

## Gradient Descent to learn the parameters in Logistic Regression

The Cost Function defined above has a convexed shape, which allows for gradient descent.

![alt text][logo6]

[logo6]: 6.png "6"


![alt text][logo7]

[logo7]: 7.png "7"

If the gradient is positive, `w` will subtract a positive number, decreasing the value of `w`

If the gradient is negative, `w` will subtract a negative number, increasing the value of `w`

Depending on which value you're updating, `w` or `b`, we take the derivative with respect to that value.

![alt text][logo8]

[logo8]: 8.png "8"

## Intuition about Derivatives

Derivative tell us the slope of the function.

The derivative value of a graph tells us how much `y` moves when `x` is moved.

When `x` moves by `0.001`, `y` moves by `d(y)/d(x) * 0.001`

## Computation Graph

A computation graph breaks down a formula to it's constituent operations, so that we can perform forward passes, and backward passes

![alt text][logo9]

[logo9]: 9.png "9"

In this example, we want to minimize `J(a,b,c)`. The blue lines are the forward pass, while the red lines are the backward pass.

Backward passes take the derivative of the computation blocks.

## Logistic Regression + Gradient Descent

Recapping our Logistic Regression steps, we can break it down to its Computation Graph

![alt text][logo10]

[logo10]: 10.png "10"


![alt text][logo11]

[logo11]: 11.png "11"

Using the computation graph, we want to minimize loss function `L(a,y)` by tweaking values `w1`, `w2` and `b`.

We can backpropagate to find the derivatives of `d(L)/d(w1)`, `d(L)/d(w2)` and `d(L)/d(b)`.

The values of `w1`, `w2` and `b` are then changed accordingly

```
w1 := w1 - a( d(L)/d(w1) )
w2 := w2 - a( d(L)/d(w2) )
b := b - a( d(L)/d(b) )
```

Where `a` is the learning rate

## Gradient Descent over multiple training examples

![alt text][logo12]

[logo12]: 12.png "12"

![alt text][logo13]

[logo13]: 13.png "13"

The draw back of this is that having huge number of features, your `for loop` will take a really long time. To tackle this, we will need to vectorize your variables.
