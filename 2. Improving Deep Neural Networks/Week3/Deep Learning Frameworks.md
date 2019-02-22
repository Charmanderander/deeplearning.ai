# TensorFlow

1. Initialize the cost function

`cost = w**2 - 10*2 + 25`

2. Initialize the gradient descent algorithm

`train = tf.train.GradientDescentOptimizer(0.01).minimize(cost)`

3. Runs one iteration of gradient descent to minimize the cost function

`session.run(train)` 

4. Feeding it data to the model

`coefficients = np.array([[1.], [-20.], [100.]])`

`session.run(train, feed_dict={x:coefficients})`
