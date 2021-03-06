#### [Word Embeddings](https://www.codecademy.com/paths/build-chatbots-with-python/tracks/retrieval-based-chatbots/modules/nlp-word-embeddings/lessons/word-embeddings/exercises/introduction)
# [Vectors](https://www.codecademy.com/paths/build-chatbots-with-python/tracks/retrieval-based-chatbots/modules/nlp-word-embeddings/lessons/word-embeddings/exercises/vectors)
Vectors are containers of information.

Depending on the size, or the dimension, of a vector, it can hold varying amounts of data.

## 1-dimensional vector
Stores a single number.

Say we want to represent the length of a word with a vector. We can do so as follows:
```
"cat" ----> [3]
"scrabble" ----> [8]
"antidisestablishmentarianism" ----> [28]
```
<img alt="one dimensional vector" src="vectors-one-dimension.webp" width="600" height="300" />

## 2-dimensional vector
Now let’s say we also want to record the number of vowels in our words, in addition to the number of letters.
```
"cat" ----> [3, 1]
"scrabble" ----> [8, 2]
"antidisestablishmentarianism" ----> [28, 11]
```
The x-axis is the number of letters, and the y-axis is the number of vowels.

<img alt="two dimensional vector" src="vectors-two-dimensions.webp" width="600" height="400" />

## Any number of dimensions
We are able to have vectors in any number of dimensions. Even 1,000!

Vectors help us summarize information about an object using numbers. Then, using the number representation, we can make comparisons between the vector representations of different objects!

This idea is central to how word embeddings map words into vectors.

We can easily represent vectors in Python using NumPy arrays. 
