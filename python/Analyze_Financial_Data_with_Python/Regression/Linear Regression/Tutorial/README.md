# Linear Regression

## [Points and Lines](https://www.codecademy.com/paths/finance-python/tracks/regression-for-finance/modules/linear-regression-python-finance/lessons/linear-regression/exercises/points-and-lines)
A line is determined by its slope and its intercept.

<a href="https://www.codecogs.com/eqnedit.php?latex=y&space;=&space;mx&space;&plus;&space;b" target="_blank"><img src="https://latex.codecogs.com/gif.latex?y&space;=&space;mx&space;&plus;&space;b" title="y = mx + b" /></a>

m: the slope<br />
b: the intercept<br />
y: a given point on the y-axis, and it corresponds to a given `x` on the x-axis

The slope is a measure of how steep the line is, while the intercept is a measure of where the line hits the y-axis.<br />
When we perform Linear Regression, the goal is to get the “best” m and b for our data.
## [Loss](https://www.codecademy.com/paths/finance-python/tracks/regression-for-finance/modules/linear-regression-python-finance/lessons/linear-regression/exercises/loss)
When we think about how we can assign a slope and intercept to fit a set of points, we have to define what the best fit is.<br />
For each data point, we calculate loss, a number that measures how bad the model’s (in this case, the line’s) prediction was.<br />
We can think about loss as the squared distance from the point to the line. We do the squared distance (instead of just the distance) so that points above and below the line both contribute to total loss in the same way:
![Image](https://content.codecademy.com/programs/machine-learning/linear-regression/points.svg)

In this example:

* For point A, the squared distance is 9 (3²)
* For point B, the squared distance is 1 (1²)

So the total loss, with this model, is 10. If we found a line that had less loss than 10, that line would be a better model for this data.
## [Minimizing Loss](https://www.codecademy.com/paths/finance-python/tracks/regression-for-finance/modules/linear-regression-python-finance/lessons/linear-regression/exercises/minimizing-loss)
The goal of a linear regression model is to find the slope and intercept pair that minimizes loss on average across all of the data.
## [Gradient Descent for Intercept (b)](https://www.codecademy.com/paths/finance-python/tracks/regression-for-finance/modules/linear-regression-python-finance/lessons/linear-regression/exercises/gradient-descent-b)
As we try to minimize loss, we take each parameter we are changing, and move it as long as we are decreasing loss. It’s like we are moving down a hill, and stop once we reach the bottom:<br />
The process by which we do this is called gradient descent. We move in the direction that decreases our loss the most. Gradient refers to the slope of the curve at any point.<br />
To find the gradient of loss as intercept changes, the formula comes out to be:<br />
<a href="https://www.codecogs.com/eqnedit.php?latex=\frac{2}{N}\sum_{i=1}^{N}-(y_{i}-(mx_{i}&plus;b))" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{2}{N}\sum_{i=1}^{N}-(y_{i}-(mx_{i}&plus;b))" title="\frac{2}{N}\sum_{i=1}^{N}-(y_{i}-(mx_{i}+b))" /></a>
* `N` is the number of points we have in our dataset
* `m` is the current gradient guess
* `b` is the current intercept guess

`get_gradient_at_b()`

## [Gradient Descent for Slope](https://www.codecademy.com/paths/finance-python/tracks/regression-for-finance/modules/linear-regression-python-finance/lessons/linear-regression/exercises/gradient-descent-m)
To find the m gradient, or the way the loss changes as the slope of our line changes, we can use this formula:<br />
<a href="https://www.codecogs.com/eqnedit.php?latex=\frac{2}{N}\sum_{i=1}^{N}-x_{i}(y_{i}-(mx_{i}&plus;b))" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{2}{N}\sum_{i=1}^{N}-x_{i}(y_{i}-(mx_{i}&plus;b))" title="\frac{2}{N}\sum_{i=1}^{N}-x_{i}(y_{i}-(mx_{i}+b))" /></a>

`get_gradient_at_m()`

## [learning rate](https://www.codecademy.com/paths/finance-python/tracks/regression-for-finance/modules/linear-regression-python-finance/lessons/linear-regression/exercises/put-together)
We can scale the size of the step by multiplying the gradient by a learning rate.<br />
`new_b = current_b - (learning_rate * b_gradient)`
* `current_b` is our guess for what the `b` value is, 
* `b_gradient` is the gradient of the loss curve at our current guess, 
* `learning_rate` is proportional to the size of the step we want to take

`step_gradient()`

We have to choose a learning rate, which will determine how far down the loss curve we go.<br />
A **small learning** rate will take a long time to converge — you might run out of time or cycles before getting an answer. <br />
A **large learning rate** might skip over the best value. It might never converge!<br />
You just have to find a learning rate large enough that gradient descent converges with the efficiency you need, and not so large that convergence never happens.
## [Convergence](https://www.codecademy.com/paths/finance-python/tracks/regression-for-finance/modules/linear-regression-python-finance/lessons/linear-regression/exercises/convergence)
How do we know when we should stop changing the parameters m and b?<br />
We have to define convergence. Convergence is when the loss stops changing (or changes very slowly) when parameters are changed.

`gradient_descent()`
