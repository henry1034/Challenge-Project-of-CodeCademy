#### RULES OF PROBABILITY

# [Introduction](https://www.codecademy.com/courses/probability-mssp/lessons/rules-of-probability/exercises/introduction)

Probability is a way to quantify uncertainty. 
When we flip a fair coin, we say that there is a 50 percent chance (probability = 0.5) of it coming up tails. 
This means that if we flip INFINITELY many fair coins, half of them will come up tails. 
Similarly, when we roll a six-sided die, we say there is a 1 in 6 chance of rolling a five.

What if we flip a coin in one hand and roll a die in the other at the same time. 
What is the probability that the coin comes up tails AND the die comes up as a five? 
Is there a way to quantify the probability that these two different events BOTH occur? 
In this lesson, we will walk through different rules of probability that help us quantify the probability of multiple random events.

# [Union, Intersection, and Complement](https://www.codecademy.com/courses/probability-mssp/lessons/rules-of-probability/exercises/union-intersection-and-complement)

Let’s dive into some key concepts we will use throughout this lesson: union, intersection, and complement.

## Union

The union of two sets encompasses **any element** that **exists** in either one or both of them. 
We can represent this visually as a *Venn diagram*.

![union-venndiagram](images/union-venndiagram.svg)

For example, let’s say we have two sets, `A` and `B`. 
* `A` represents rolling an odd number with a six-sided die (the set {1, 3, 5}). 
* `B` represents rolling a number greater than two (the set {3, 4, 5, 6}). 

The union of these two sets would be everything in either set `A`, set `B`, or both: {1, 3, 4, 5, 6}. 
We can write the union of two events mathematically as **(A or B)**.

## Intersection

The intersection of two sets encompasses **any element** that **exists in both** of the sets. 
Visually:

![intersection venndiagram](images/intersection-venndiagram.svg)

The intersection of the above sets (`A` represents rolling an odd number on a six-sided die and `B` represents rolling a number greater than two) 
includes any value that appears in both sets: {3, 5}. 
We can write the union of two events mathematically as **(A and B)**.

## Complement

Lastly, the complement of a set consists of **all possible outcomes outside of the set**. 
Visually:

![complement venndiagram](images/complement-venndiagram.svg)

Consider set `A` from the above example (rolling an odd number on a 6-sided die). 
The complement of this set would be rolling an even number: {2, 4, 6}. 
We can write the complement of set `A` as `A`<sup>`C`</sup>. 
One key feature of complements is that **a set and its complement cover the entire sample space**. 
In this die roll example, **the set of even numbers and odd numbers** would **cover all possible rolls**: {1, 2, 3, 4, 5, 6}.

# [Independence and Dependence](https://www.codecademy.com/courses/probability-mssp/lessons/rules-of-probability/exercises/independence-and-dependence)

Imagine that we flip a fair coin 5 times and get 5 heads in a row. 
Does this affect the probability of getting heads on the next flip? 
Even though we may feel like it’s time to see “tails”, it is impossible for a past coin flip to impact a future one. 
The fact that **previous** coin flips **do not affect future ones** is called **independence**. 

### Two events are independent if the occurrence of one event does not affect the probability of the other.

Are there cases where previous events do affect the outcome of the next event? 
Suppose we have a bag of five marbles: two marbles are blue and three marbles are red. 
If we take one marble out of the bag, what is the probability that the second marble we take out is blue?

![dependent event](images/marble-diagram-1.svg)

This describes two events that are **dependent**. 
The probability of grabbing a blue marble in the second event depends on whether we take out a red or a blue marble in the first event.

What if we had put back the first marble? 
Is the probability that we pick a blue marble second independent or dependent on what we pick out first? 
In this case, the events would be **independent**.

![independent event](images/marble-diagram-2.svg)

Why do we care if events are independent or dependent? 
Knowing this helps us quantify the probability of events that depend on preexisting knowledge. 
This helps researchers understand and predict complex processes such as:
* Effectiveness of vaccines
* The weather on a particular day
* Betting odds for professional sports games

We will explore applications of this further in the lesson!

<hr />

We pick out two cards from a standard deck of 52 cards without replacement. 
* **Event A** is that we pick an Ace on the first draw. 
* **Event B** is that we pick an Ace on the second draw.
<details>
  <summary>Are events A and B independent?</summary>
  Not, they are dependent.
</details>
<hr />

Suppose we roll a six-sided die two times. 
* **Event A** is that we roll a 3 on the first roll. 
* **Event B** is that we roll a 3 on the second roll. Are events A and B independent?
<details>
  <summary>Are events A and B independent?</summary>
  Yes, they are independent.
</details>
<hr />

Suppose we flip a coin ten times. 
* **Event A** is that we flip all heads on the first five flips. 
* **Event B** is that we flip all heads on the second five flips. 
<details>
  <summary>Are events A and B independent?</summary>
  Yes, they are independent.
</details>

# [Mutually Exclusive Events](https://www.codecademy.com/courses/probability-mssp/lessons/rules-of-probability/exercises/mutually-exclusive-events)

### Two events are considered mutually exclusive if they cannot occur at the same time. 

For example, consider a single coin flip: the events “tails” and “heads” are mutually exclusive because we cannot get both tails and heads on a single flip.

We can visualize two mutually exclusive events as a pair of non-overlapping circles. 
They do not overlap because there is no outcome for one event that is also in the sample space for the other:

![mutually exclusive venndiagram](images/mutually-exclusive-venndiagram.svg)

What about events that are **not mutually exclusive**? 
If event `A` is rolling an odd number and event `B` is rolling a number greater than two, these events are not mutually exclusive. 
**They have** an **intersection** of {3, 5}. 

### Any events that have a non-empty intersection are not mutually exclusive.

<hr />

We have a bag of five marbles: three are green and two are blue. 
Suppose that we pick one marble from the bag. 
* **Event A** is that the marble is green. 
* **Event B** is that the marble is blue.
<details>
  <summary>Are these events mutually exclusive?</summary>
  Yes, they are mutually exclusive.
</details>
<hr />

We roll a die once. 
* **Event A** is rolling an odd number. 
* **Event B** is rolling a number greater than four.
<details>
  <summary>Are these events mutually exclusive?</summary>
  Not, they are not mutually exclusive.
</details>
<hr />

We roll a die once. 
* **Event A** is rolling an even number. 
* **Event B** is rolling a number less than two. 
<details>
  <summary>Are these events mutually exclusive?</summary>
  Yes, they are mutually exclusive.
</details>
<hr />

# [Addition Rule](https://www.codecademy.com/courses/probability-mssp/lessons/rules-of-probability/exercises/addition-rule)

Now, it’s time to apply these concepts to calculate probabilities.

Let’s go back to one of our first examples: 
* **event A** is rolling an odd number on a six-sided die and 
* **event B** is rolling a number greater than two. 

What if we want to find the probability of one or both events occurring? 
This is the **probability of the union of A and B**:

<h4 align="center">
  P(A or B)
</h4>

We can visualize this calculation as follows:

<img alt="the probability of the union of A and B" src="images/addition-rule-independent-venndiagram.webp" width="600px" />

**Probability of the union of A and B = Probability A + Probability B - Probability of the intersection of A and B**

This animation gives a visual representation of the addition rule formula, which is:

<p align="center">
  <img alt="the probability of the union of A and B formula" src="images/the_probability_of_the_union_of_A_and_B_formula.svg" />
</p>

We subtract the intersection of events `A` and `B` because it is included twice in the addition of P(A) and P(B).

What if the events are mutually exclusive? 
On a single die roll, if event `A` is that the roll is less than or equal to 2 and event `B` is that the roll is greater than or equal to 5, 
then events `A` and `B` cannot both happen.

<img alt="the probability of the union of A and B when they are mutually exclusive" src="images/addition-rule-dependent-venndiagram.webp" width="600px" />

For mutually exclusive events, the addition rule formula is:

<p align="center">
  <img alt="mutually exclusive events formula" src="images/mutually_exclusive_events_formula.svg" />
</p>

This is because the **intersection is empty**, so we don’t need to remove any overlap between the two events.

# [Conditional Probability](https://www.codecademy.com/courses/probability-mssp/lessons/rules-of-probability/exercises/conditional-probability)

If we want to calculate the probability that a pair of dependent events both occur, we need to define conditional probability. 
Using a bag of marbles as an example, let’s remind ourselves of the definition of **dependent events**:

![dependent event](images/marble-diagram-1.svg)

If we pick two marbles from a bag of five marbles without replacement, the probability that the second marble is red depends on the color of the first marble. 
We have a special name for this: **conditional probability**. 
In short, conditional probability measures the probability of one event occurring, given that another one has already occurred.

Notationally, we denote the word “given” with a vertical line. 
For example, if we want to represent the probability that we choose a red marble given the first marble is blue, we can write:

<p align="center">
  <img alt="conditional probability" src="images/conditional_probability.svg" />
</p>

From the above diagram, we know that:

<p align="center">
  <img alt="3 in 4" src="images/conditional_probability_3_in_4.svg" />
</p>

What if we picked out two marbles with replacement? 
What does the conditional probability look like? 
Well, let’s think about this. 
Regardless of which marble we pick out first, it will be put back into the bag. 
Therefore, the probability of picking out a red marble or a blue marble second is unaffected by the first outcome.

Therefore, for independent events, we can say the following:

<p align="center">
  <img alt="Probability of B first A second" src="images/p_of_b_first_a_second.svg" />
  <br />and<br />
  <img alt="Probability of A first B second" src="images/p_of_a_first_b_second.svg" />
</p>

# [Multiplication Rule](https://www.codecademy.com/courses/probability-mssp/lessons/rules-of-probability/exercises/multiplication-rule)

We have looked at the addition rule, which describes the probability one event OR another event (or both) occurs. 
What if we want to calculate the probability that two events happen simultaneously? 
For two events, `A` and `B`, this is `P(A and B)` or the **probability of the intersection of A and B**.

## General Formula

The general formula for the probability that two events occur simultaneously is:

<p align="center">
  <img alt="the probability of the intersection of A and B" src="images/p_a_and_b.svg" />
</p>

However, for independent events, we can simplify this formula slightly.

## Dependent Events

Let’s go back to our bag of marbles example. 
We have five marbles: 
* two are blue, 
* and three are red. 

We pick two marbles without replacement. 
What if we want to know the probability of choosing a *blue marble first AND a blue marble second*?

Taking conditional probability into account, the multiplication rule for these two dependent events is:

<p align="center">
  <img alt="the probability of the intersection of A and B example 1" src="images/p_a_and_b_example_1.svg" /><br />
  <img alt="the probability of the intersection of A and B example 2" src="images/p_a_and_b_example_2.svg" /><br />
  <img alt="the probability of the intersection of A and B example 3" src="images/p_a_and_b_example_3.svg" /><br />
</p>

This is one potential outcome when picking two marbles out of the bag. 
One way to visualize all possible outcomes of a pair of events is a tree diagram.

Tree diagrams have the following properties:
* Each branch represents a specific set of events.
* The probabilities the terminal branches (all possible sets of outcomes) sum to one.
* We multiply across branches (using the multiplication rule!) to calculate the probability that each branch (set of outcomes) will occur.

## Independent Event]

For two independent events, the multiplication rule becomes less complicated. 
The probability of two independent events occurring is:

<p align="center">
  <img alt="the probability of the intersection of A and B independent" src="images/p_a_and_b_independent.svg" />
</p>

This is because the following is true for independent events:

<p align="center">
  <img alt="the probability of the intersection of A and B independent" src="images/p_a_and_b_independent_2.svg" />
</p>

Let’s look at the simplest example: flipping a fair coin twice. 
* **Event A** is that we get tails on the first flip, 
* and **event B** is that we get tails on the second flip. 

<p align="center">
  <img alt="the probability of the intersection of A and B independent example" src="images/p_a_and_b_independent_example.svg" />
</p>

, so according to our formula, the probability of getting tails on both flips would be:

<p align="center">
  <img alt="the probability of the intersection of A and B independent example result" src="images/p_a_and_b_independent_example_result.svg" />
</p>

Visually on a tree diagram, we see:

<p align="center">
  <img alt="Coin tree-diagram" src="images/coin-tree-diagram.svg" width="800px" />
</p>

# [Conditional Probability Continued](https://www.codecademy.com/courses/probability-mssp/lessons/rules-of-probability/exercises/application-conditional-probability)

We have introduced conditional probability as a part of the multiplication rule for dependent events. 
However, let’s go a bit more in-depth with it as it is a powerful probability tool that has real-world applications.

For this problem, we will follow along the tree diagram on bellow.

<p align="center">
  <img alt="conditional prob tree" src="images/conditional_prob_tree.svg" />
</p>

Suppose that the following is true (this is shown in the first set of branches in the diagram):
* 20 percent of the population has strep throat.
* 80 percent of the population does not have strep throat.

Now suppose that we test a bunch of people for strep throat. 
The possible results of these tests are shown in the next set of branches:
* If a person has strep throat, there is an 85% chance their test will be positive and a 15% chance it will be negative. 
This is labeled as:

<p align="center">
  <img alt="Strep troat positive" src="images/strep_troat_pos.svg" /><br />
  and<br />
  <img alt="Strep troat negative" src="images/strep_troat_neg.svg" /><br />
</p>

* If a person does not have strep throat, there is a 98% chance their test will be negative and a 2% chance it will be positive. This can be labeled as:

<p align="center">
  <img alt="No Strep troat negative" src="images/no_strep_troat_neg.svg" /><br />
  and<br />
  <img alt="No Strep troat positiv" src="images/no_strep_troat_pos.svg" /><br />
</p>

Finally, let’s look at the four possible pairs of outcomes that form the terminal branches of our diagram:
<p align="center">
  <img alt="Probability of Strep troat and positive" src="images/p_strep_troat_and_pos.svg" /><br />
  <img alt="Probability of Strep troat and negative" src="images/p_strep_troat_and_neg.svg" /><br />
  <img alt="Probability of No Strep troat and positive" src="images/p_no_strep_troat_and_pos.svg" /><br />
  <img alt="Probability of No Strep troat and negative" src="images/p_no_strep_troat_and_neg.svg" /><br />
</p>

Together, these add up to one since they capture all potential outcomes after patients are tested.

It’s great that we have all this information. 
However, we are missing something. 
If someone gets a positive result, what is the probability that they have strep throat? 
Notationally, we can write this probability as:

<p align="center">
  <img alt="Probability of Positive Test and Strep Troat" src="images/p_pos_and_st.svg" />
</p>

In the next exercise, we’ll explore how we can use our tree diagram to calculate this probability.

# [Bayes' Theorem](https://www.codecademy.com/courses/probability-mssp/lessons/rules-of-probability/exercises/bayes-theorem)

Imagine that you are a patient who has recently tested positive for strep throat. 
You may want to know the probability that you HAVE strep throat, given that you tested positive:

<p align="center">
  <img alt="Probability of Positive Test and Strep Troat" src="images/p_pos_and_st.svg" />
</p>

To calculate this probability, we will use something called ***Bayes Theorem***, which states the following:

<p align="center">
  <img alt="Bayes Theorem formula" src="images/bayes_theorem_formula.svg" />
</p>

Using Bayes’ theorem:

<p align="center">
  <img alt="Bayes Theorem example" src="images/bayes_theorem_example.svg" />
</p>

We know:

<p align="center">
  <img alt="Bayes Theorem example" src="images/bayes_theorem_example.svg" />
</p>


