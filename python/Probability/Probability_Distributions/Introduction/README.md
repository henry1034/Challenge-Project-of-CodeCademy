#### INTRODUCTION TO PROBABILITY DISTRIBUTIONS

# [Random Variables](https://www.codecademy.com/courses/probability-mssp/lessons/introduction-to-probability-distributions/exercises/random-variables)

A random variable is, in its simplest form, a function. 
It can equal any possible outcome from the sample space of an event.

Random variables must be numeric, meaning they always take on a number rather than a characteristic or quality. 
For example, when rolling a six-sided fair die, the random variable would be the number (between 1 and 6) from the resulting roll.

If the observed event does not have a numeric outcome, we can assign the random variable to equal 1 if there is a specific outcome and 0 otherwise. 
For example, when observing a fair coin flip, we can assign a “heads” to be the value 1 and a “tails” to be the value 0.

We will be using `random.choice(a, size = size, replace = True/False)` from the `numpy` library to simulate random variables in python. 
In this method:
* `a` is a list or other object that has values we are sampling from
* `size` is a number that represents how many values to  choose
* `replace` will equal either `True` or `False` to represent whether 
  * we will keep a value in a after drawing it (`replace = True`) 
  * or if we remove it from the pool (`replace = False`). 
If we were to roll a die multiple times, we would use `replace = True` because we don’t remove a value after observing it. 
But if we were to draw a card and leave it out of the deck before drawing again, we would do `replace = False`.

The following code simulates the outcome of rolling a fair die twice using `np.random.choice()`:
```py
import numpy as np
 
# 7 is not included in the range function
die_6 = range(1, 7)
 
rolls = np.random.choice(die_6, size = 2, replace = True)
 
print(rolls)
Output:

# [2, 5]
```

# [Discrete and Continuous Random Variables](https://www.codecademy.com/courses/probability-mssp/lessons/introduction-to-probability-distributions/exercises/discrete-and-continuous-random-variables)

## Discrete Random Variables

**When the possible values in a sample space are countable**, the random variable is called a discrete random variable. 
For example, rolling a regular 6-sided die would be considered a discrete random variable because the outcome options are limited to the numbers on the die.

Discrete random variables are also common when observing counting events, such as how many people entered a store on a randomly selected day. 
In this case, the values are countable in that they are limited to whole numbers (you can’t observe half of a person).

## Continuous Random Variables

**When the possible values in a sample space are uncountable**, the random variable is called a continuous random variable. 
These are generally measurement variables and are uncountable because measurements can always be more precise – meters, centimeters, millimeters, etc.

For example, the temperature in Los Angeles on a randomly chosen day is a continuous random variable. 
The temperature measurement can always extend to another decimal place (96 degrees, 96.44 degrees, 96.437 degrees, etc.).

# [Probability Mass Functions](https://www.codecademy.com/courses/probability-mssp/lessons/introduction-to-probability-distributions/exercises/probability-mass-functions)

The probability mass function (PMF) defines the specific probability distribution of the random variable. 
It is used to calculate the probability that a specific event from a discrete random variable occurs. 
For example, a PMF can be used to calculate the probability of rolling a three from a fair six-sided die.

Probability distributions explain the probabilities of observing the possible outcomes of an event. 
There are many different probability distributions. 
Each distribution has its own parameters that describe specific random events. 
You may be familiar with some of these parameters, like the mean and standard deviation, that define some of the most commonly used distributions in statistics.

For example, the distribution for flipping a fair coin ten times and counting the number of heads we observe is called a *binomial distribution*. 
The parameters for the binomial distribution are:
* `n` for the sample size (number of observations, in this case: ten coin flips)
* `p` for the probability of success (probability of seeing our determined outcome, in this case: the probability of seeing heads is 0.5)

This experiment would be classified as a `Binomial(n = 10, p = 0.5)` distribution. 
The graph below shows the probability mass function for this experiment. 
The heights of the bars represent the probability of observing each possible outcome as calculated by the PMF.

![Binom PMF](binom_pmf_10_5.svg)





























