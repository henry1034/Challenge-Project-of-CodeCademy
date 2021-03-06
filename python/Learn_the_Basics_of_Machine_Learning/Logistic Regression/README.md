# [Introduction](https://www.codecademy.com/courses/machine-learning/lessons/logistic-regression/exercises/introduction)
Logistic Regression is a supervised machine learning algorithm that uses regression to predict the continuous probability, ranging from `0` to `1`, of a data sample belonging to a specific category, or class.
Then, based on that probability, the sample is classified as belonging to the more probable class, ultimately making Logistic Regression a classification algorithm.

The output of a Linear Regression model ranges from -∞ to +∞.
The output of a Linear Regression model does not provide the probabilities we need to predict (`0` or `1`).

# [Logistic Regression](https://www.codecademy.com/courses/machine-learning/lessons/logistic-regression/exercises/logistic)
In Logistic Regression we are also looking to find coefficients for our features, but this time we are fitting a logistic curve to the data so that we can predict probabilities.

To predict the probability of a data sample belonging to a class, we:
1. initialize all feature coefficients and intercept to `0`
2. multiply each of the feature coefficients by their respective feature value to get what is known as the *log-odds*
3. place the log-odds into the sigmoid function to link the output to the range `[0, 1]`, giving us a probability

By comparing the predicted probabilities to the actual classes of our data points, we can evaluate how well our model makes predictions and use [gradient descent](https://github.com/lendoo73/Challenge-Project-of-CodeCademy/tree/master/python/Analyze_Financial_Data_with_Python/Regression/Linear%20Regression/Tutorial) to update the coefficients and find the best ones for our model.

To then make a final classification, we use a classification threshold to determine whether the data sample belongs to the positive class or the negative class.

# [Log-Odds](https://www.codecademy.com/courses/machine-learning/lessons/logistic-regression/exercises/log-odds)
In Linear Regression we multiply the coefficients of our features by their respective feature values and add the intercept, resulting in our prediction, which can range from -∞ to +∞.

In Logistic Regression, we make the same multiplication of feature coefficients and feature values and add the intercept, but instead of the prediction, we get what is called the **log-odds**.

The log-odds are another way of expressing the probability of a sample belonging to the positive class, or a student passing the exam.
In probability, we calculate the odds of an event occurring as follows:

![odds](odds.jpg)

The odds tell us how many more times likely an event is to occur than not occur.

The log-odds are then understood as the logarithm of the odds!
```
def log_odds(features, coefficients, intercept):
  return np.dot(features, coefficients) + intercept
```

# [Sigmoid Function](https://www.codecademy.com/courses/machine-learning/lessons/logistic-regression/exercises/sigmoid)

![sigmoid](sigmoid.webp)

The Sigmoid Function is a special case of the more general Logistic Function, where Logistic Regression gets its name.
By plugging the log-odds into the Sigmoid Function, defined below, we map the log-odds `z` to the range `[0, 1]`.

![sigmoid function](sigmoid_function.jpg)

* e<sup>-z</sup> is the exponential function, which can be written in `numpy` as `np.exp(-z)`

This enables our Logistic Regression model to output the probability of a sample belonging to the positive class.
```
def sigmoid(z):
  denominator = 1 + np.exp(-z)
  return 1 / denominator
```

# [Log-Loss](https://www.codecademy.com/courses/machine-learning/lessons/logistic-regression/exercises/log-loss-i)
We need a way to evaluate how well a given model fits the data we have.

The function used to evaluate the performance of a machine learning model is called a *loss function*, or a *cost function*.
To evaluate how “good a fit” a model is, we calculate the loss for each data sample (how wrong the model’s prediction was) and then average the loss across all samples.
The loss function for Logistic Regression, known as **Log Loss**:

![log loss](log_loss.jpg)

* `m`: the total number of data samples
* `y`<sup>`(i)`</sup>: the class of data sample `i`
* `z`<sup>`(i)`</sup>: the log-odds of sample `i`
* `h(z`<sup>`(i)`</sup>`)`: the sigmoid of the log-odds of sample `i`, which is the probability of sample `i` belonging to the positive class

The goal of our Logistic Regression model is to find the feature coefficients and intercept, which shape the logistic function, that minimize log-loss for our training data!

Let’s go ahead and break down our log-loss function into two separate parts so it begins to make more sense. 
Consider the case when a data sample has class y = 1, or for our data when a student passed the exam. 
The right-side of the equation drops out because we end up with `1 - 1` (or `0` => (1 - y<sup>(i)</sup>) ) multiplied by some value.
The loss for that individual student becomes:

![when a student passed the exam](loss_y_1.jpg)

The loss for a student who passed the exam is just the log of the probability the student passed the exam!

And for a student who fails the exam, where a sample has class y = 0, the left-side of the equation drops out and the loss for that student becomes:

![student who fails the exam](loss_y_0.jpg)

The loss for a student who failed the exam is the log of one minus the probability the student passed the exam, which is just the log of the probability the student failed the exam!

Let’s take a closer look at what is going on with our loss function by graphing the loss of individual samples when the class label is y = 1 and y = 0.

![loss function graph](loss-function-graph.webp)

From the graphs you can see that confident correct predictions result in small losses, while confident incorrect predictions result in large losses that approach infinity.
We want to punish our model with an increasing loss as it makes progressively incorrect predictions, and we want to reward the model with a small loss as it makes correct predictions.

Just like in Linear Regression, we can then use gradient descent to find the coefficients that minimize log-loss across all of our training data.

# [Classification Thresholding](https://www.codecademy.com/courses/machine-learning/lessons/logistic-regression/exercises/thresholding)
Many machine learning algorithms, including Logistic Regression, spit out a classification probability as their result.
Once we have this probability, we need to make a decision on what class the sample belongs to. 
This is where the **classification threshold** comes in!

The default threshold for many algorithms is `0.5`.
If the predicted probability of an observation belonging to the positive class is greater than or equal to the threshold, 0.5, the classification of the sample is the positive class.
If the predicted probability of an observation belonging to the positive class is less than the threshold, 0.5, the classification of the sample is the negative class.

We can choose to change the threshold of classification based on the use-case of our model. 

# [Logistic Regression models with sklearn](https://www.codecademy.com/courses/machine-learning/lessons/logistic-regression/exercises/scikit-learn)
We can begin by creating a `LogisticRegression` object.
```
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()
```
After creating the object, we need to fit our model on the data. 
When we fit the model with `sklearn` it will perform gradient descent, repeatedly updating the coefficients of our model in order to minimize the log-loss. 
We train — or fit — the model using the `.fit()` method, which takes two parameters. The first is a matrix of features, and the second is a matrix of class labels.
```
model.fit(features, labels)
```
Now that the model is trained, we can access a few useful attributes of the `LogisticRegression` object:
* `model.coef_`: a vector of the coefficients of each feature
* `model.intercept_`: the intercept b_0

With our trained model we are able to predict whether new data points belong to the positive class using the `.predict()` method!
`.predict()` takes a matrix of features as a parameter and returns a vector of labels `1` or `0` for each sample. 
In making its predictions, `sklearn` uses a classification threshold of `0.5`.
```
model.predict(features)
```
If we are more interested in the predicted probability of the data samples belonging to the positive class than the actual class, we can use the `.predict_proba()` method.
`.predict_proba()` also takes a matrix of features as a parameter and returns a vector of probabilities, ranging from `0` to `1`, for each sample.
```
model.predict_proba(features)
```
Before proceeding, one important note is that `sklearn`‘s Logistic Regression implementation requires feature data to be normalized.
[Normalization](https://github.com/lendoo73/Challenge-Project-of-CodeCademy/tree/master/python/Learn_the_Basics_of_Machine_Learning/Classification_K_Nearest_Neighbors/Normalization) scales all feature data to vary over the same range.
`sklearn`‘s Logistic Regression requires normalized feature data due to a technique called *Regularization* that it uses under the hood. 

# [Feature Importance](https://www.codecademy.com/courses/machine-learning/lessons/logistic-regression/exercises/feature-importance)
Since our data is normalized, all features vary over the same range.
Given this understanding, we can compare the feature coefficients’ magnitudes and signs to determine which features have the greatest impact on class prediction, and if that impact is positive or negative.
* Features with larger, positive coefficients will increase the probability of a data sample belonging to the positive class
* Features with larger, negative coefficients will decrease the probability of a data sample belonging to the positive class
* Features with small, positive or negative coefficients have minimal impact on the probability of a data sample belonging to the positive class

