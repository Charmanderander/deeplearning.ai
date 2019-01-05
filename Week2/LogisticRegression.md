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
