---
title: "My Learning Path to (Finally) Understanding LLMs: Relations and Functions"
date: 2025-03-06
draft: false
author: "Arturo Bermejo"
tags: ["technology", "llms", "artificial intelligence"]
language: "en"
post_id: "llms-my-learning-way-part-1"
slug: "my-learning-path-llms-relations-and-functions"
lang_link: "/blog/mi-camino-entender-llms-relaciones-y-funciones/"
---

![relations and functions](/images/llms-my-learning-way-part-1.jpg)

Our daily life is full of variables that depend on each other, from how sleep quality affects your health to how weather affects your mood. Essentially, it's about how things connect and influence each other.

Artificial intelligence is often perceived as a very abstract topic, but we could argue that at its core, it's all about these same dependency relationships: how data connects, how patterns emerge, and how results are obtained from them. Therefore, it's very useful to start by understanding how these relationships are founded and represented to comprehend how artificial intelligence models work.

Although mathematics can seem intimidating, when viewed in context, they become a fundamental tool for better understanding and internalizing ideas. In this sense, the concept of function is the basis for representing these relationships in a numerical and precise way. A function then allows us to model the relationship between one or more independent variables and a dependent variable.

Let's imagine we want to understand how our happiness depends on two factors: the number of friends we have and the amount of money we possess. To represent this relationship, we can use a mathematical function.

For example, let's consider the following function:

\[
f(x, y) = 2x + 5y
\]

Where:
- x: represents the amount of money.
- y: represents the number of friends.
<br><br>

This function tells us that our happiness is influenced by both money and friends, but to different degrees. According to this formula, each unit of money adds 2 points to happiness, while each friend adds 5 points. In other words, the function suggests that friends have a greater impact on happiness than money.

The concept of function is key because it allows us to model dependency relationships in different contexts. Whenever one or more variables influence a result, a function can help us represent it precisely and comprehensibly.

### The text generation problem

In models like GPT, we also find these relationships. We can view these models as functions whose objective is to predict or generate a word based on another list of previous words, that is, to predict the next word in a sentence coherently.

For example, if we have the sentence:

> "The sky is…"

we might expect the next generated word to be "blue," although other options like "gray" or "cloudy" could also emerge, depending on the context of the current sentence.

In reality, in this process, the model doesn't work solely with complete words, but with tokens, which can represent a word, part of a word, or even a symbol, but for now let's consider them as words.

So we can see that there's a dependency relationship between the given sentence and the word to be generated, which we can represent with the following mathematical notation that corresponds to a function:

\[
\text{next_word} = f(\text{sentence})
\]

Although it may seem like a very drastic simplification, at the end of the day it's simply a function. Not a simple function clearly, but a function nonetheless.

Now let's ask ourselves: What else does a model's ability to generate the next word optimally depend on?

We can intuit that it depends on two fundamental components:

1. **The current sentence**, as we already saw, provides the immediate context and defines the possible words that can follow.

2. **Language knowledge**, understood as the set of rules and patterns that the model "knows." This includes grammar, sentence structure, word meaning (semantics), and the relationship between concepts.

For example, if we have the sentence:

> "Today I carry an umbrella because the sky is…"

the model must analyze the structure and meaning of the sentence, but also apply its previous knowledge about weather and language use to predict words like "cloudy" or "rainy," instead of something unrelated like "happy."

We can then see two elements working together: the current sentence defines the immediate context, while knowledge guides the selection of the most appropriate word.

With this idea in mind, we can modify our function to reflect that generating the next word depends not only on the current sentence, but also on previous language knowledge:

\[
y = f(x, w)
\]

Where:
- \(x\): represents the current sentence or phrase.
- \(w\): is the language knowledge.
- \(y\): is the next generated word.
<br><br>

This same principle can be applied in many other scenarios where a decision depends on both present information and accumulated knowledge.

Let's take a chess game as an example. Our next move depends not only on the moves that have occurred in the current game (x), but also on our previous knowledge about strategies, openings, and game patterns (w). This knowledge allows us to evaluate which moves (y) are more favorable and which could lead us to a disadvantage.

### A first model

With the concepts we've seen so far, let's think: How can I now define my model?

Given that x is the input and y is the output of our model, there are only two aspects we can define for our model:

- The value or values of w, which represents the model's knowledge.
- The form of the function, which defines how x and w interact to generate the output.
<br><br>

The function form is the model's structure, what we could call "the architecture," which would simply be the mathematical operations that make up this model. That is, the function could be composed of many other functions internally.

But how do we find the appropriate values for w? This is where the concept of training comes into play. Training a model means progressively adjusting the values of w, based on previous examples, until the model manages to make accurate predictions. That is, to obtain that "knowledge" we were talking about.

During training, w is not fixed; it's a set of values that we'll adjust so the model can make better predictions. But once the model is trained, this value of w is fixed for predicting the next word, as it's already considered optimal for any value of x.

For now, let's think of w as values we can modify arbitrarily.

Let's ground mathematically what we've discussed so far.

We had said that our model is defined as:

\[
y = f(x, w)
\]

But there's a problem: mathematical functions work with numbers, while language is composed of words. To be able to operate mathematically, we need to find a way to represent words as numbers.

A simple way to do this is to assign a numerical identifier to each word in a given set. For example:

blue → 227 <br>
sky → 350 <br>
cold → 402 <br>
the → 578 <br>
is → 698 <br>

Now, we can redefine our function to operate with these numerical representations. We assume for now that our model is already optimal, so the parameters w are constants.

\[
f(x_1, x_2, x_3) = x_1 w_1 + x_2 w_2 + x_3 w_3
\]

Here, we use three input words

\[
x_1, x_2, x_3
\]

and three associated knowledge values

\[
w_1, w_2, w_3
\]

that will act as weights in the function, assigning greater influence to one word or another.

Let's calculate the result with the following values:

\[
w_1 = 1
\]
\[
w_2 = 1.5
\]
\[
w_3 = 0.5
\]

If we take the sentence "The sky is", their values would be:

\[
x_1 = 578
\]
\[
x_2 = 698
\]
\[
x_3 = 350
\]

Substituting them in our function:

\[
\begin{align*}
f(578, 350, 698) &= 578 \times 1 - 350 \times 1.5 + 698 \times 0.5 \\
                 &= 578 - 525 + 349 \\
                 &= 402
\end{align*}
\]

The result is 402, which in our word list corresponds to "cold", forming the sentence:

> "The sky is cold"

Now, let's try another set of weights, changing w_2 to 2.0 instead of 1.5:

\[
\begin{align*}
f(578, 350, 698) &= 578 \times 1 - 350 \times 2.0 + 698 \times 0.5 \\
                 &= 578 - 700 + 349 \\
                 &= 227
\end{align*}
\]

The result is now 227, which corresponds to the word "blue", forming the sentence:

> "The sky is blue",

which seems like a better choice in this context.

This example shows us how the choice of w values affects the generated word. If we find the correct values, the model can generate more coherent sentences. This is achieved through the training process.
