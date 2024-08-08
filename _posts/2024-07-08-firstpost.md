---
title: "Probability Distributions in Data Science" 
date: 2024-08-07 00:19:00 
categories: [Statistics for DS]
tags: [Statistics]
---

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>

<script>
  MathJax = {
    tex: {
      inlineMath: [['$', '$']]
    }
  };
</script>

# Probability Distributions in Data Science


## An introduction to some of the most commonly used Probability Distributions in Data Science with real-life examples.


### Introduction

Having a sound statistical background can be greatly beneficial in the daily life of a Data Scientist. Every time we start exploring a new dataset, we need to first do an Exploratory Data Analysis (EDA) in order to get a feeling of what are the main characteristics of certain features. If we are able to understand if it’s present any pattern in the data distribution, we can then tailor-made our Machine Learning models to best fit our case study. In this way, we will be able to get a better result in less time (reducing the optimisation steps). In fact, some Machine Learning models are designed to work best under some distribution assumptions. Therefore, knowing with which distributions we are working with, can help us to identify which models are best to use.

Before introducing some important distributions, it is important to highlight some important concepts such as: Cumulative Distribution Function, Probability mass function and Probability density function.

#### Cumulative Distribution Function

The cumulative distribution function or cdf of a random variable X, denoted by F(x), is defined by : 
<div style="border: 1px solid #ccc; padding: 10px; text-align: center; width: fit-content; margin: 0 auto;">
  F(x) = P(X≤x) , for all x 
</div> <br><br>

![CDF](assets/images/cdf1.png)
*Figure 1: Example of the application of a cdf [1]*

Visually the previous example is given by:

![CDF](assets/images/cdf2.png)
*Figure 2: Example of the application of a cdf [2]*

#### Probability mass function 

The probability mass function of a discrete random variable X, denoted by f(x), is given by : 
<div style="border: 1px solid #ccc; padding: 10px; text-align: center; width: fit-content; margin: 0 auto;">
   $$ f(x) = P(X=x), for~all~x $$
</div> <br><br>

The probability density function of a continuous random variable X, is the function that satisfies: 
<div style="border: 1px solid #ccc; padding: 10px; text-align: center; width: fit-content; margin: 0 auto;">
  $$ F(x) = \int_{-\infty}^{x} f(t) \, dt $$
</div> <br><br>

For a more in depth explanation of the pdf function:

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/ZA4JkHKZM50/0.jpg)](https://www.youtube.com/watch?v=ZA4JkHKZM50&t=183s)


### Different types of data

Every time we are working with a dataset, our dataset represent a **sample** from a **population**. Using this sample, we can then try to understand it’s main patterns so that we can use it to make predictions on the whole population (even though we never had the opportunity to examine the whole population).

Let’s imagine we want to predict the price of a house given a certain set of features. We might be able to find online a dataset with all the house prices of San Francisco (our sample) and after performing some statistical analysis, we might be able to make quite accurate predictions of the house price in any other city in the USA (our population).

Datasets are composed of two main types of data: **Numerical** (eg. integers, floats), and **Categorical** (eg. names, laptops brands). 

Numerical data can additionally be divided into other two categories: **Discrete** and **Continue**. Discrete data can take only certain values (eg. number of students in a school) while continuous data can take any real or fractional value (eg. the concepts of height and weights).

From discrete random variables, it is possible to calculate **Probability Mass Functions**, while from continuous random variables can be derived **Probability Density Functions**.

Probability Mass Functions gives the probability that a variable can be equal to a certain value, instead, the values of Probability Density Functions are not itself probabilities because they need first to be integrated over the given range.

There exist many different probability distributions in nature (Figure 1), in this article I will introduce you to the ones most commonly used in Data Science.

![Distribuições de Probabilidades](assets/images/distribuicoes.png)
*Figure 3: Probability Distributions Flowchart [3]*

Throughout this article, I will provide code snippets on how to create each of the different distributions.

First of all, let’s import all the necessary libraries:

<script src="https://gist.github.com/alexandregsg/a64f9843c391f0b561805d365000dfaa.js"></script>

### Discrete distributions

#### Bernoulli distribution

The Bernoulli distribution is one of the easiest distributions to understand and can be used as a starting point to derive more complex distributions.

This distribution has only two possible outcomes and a single trial. Less formally, it can be thought as a model for the set of possible outcomes of any single experiment that asks a yes/no question -> **boolean-valued outcomes**: 1 = sucess/yes with a probability (p) ; 0 = failure/no with a probability of (q = 1-p ).


If a X random variable with this distribution , X ~ Ber(p) then:

<div style="border: 1px solid #ccc; padding: 10px; text-align: center; width: fit-content; margin: 0 auto;">
  $$ P(X=1) = p = 1 - P(X=0) = 1 - q  $$
</div> <br><br>

The pdf of this distribution , over possible outcomes x is:

<div style="border: 1px solid #ccc; padding: 10px; text-align: center; width: fit-content; margin: 0 auto;">
$$ f(x) = p^{x} \cdot (1 - p)^{1 - x} \quad \text{for } x \in \{0, 1\} $$
</div>

##### Bernoulli distribution properties

$$ Mean: E[X] = P(X = 1) \cdot 1 + P(X = 0) \cdot 0 = p \cdot 1 + q \cdot 0 = p $$

**Variance:** 

$$ E[X^2] = P(X = 1) \cdot 1^2 + P(X = 0) \cdot 0^2 = p \cdot 1 + q \cdot 0 = p $$

$$ Var[X] = E[X^2] - (E[X])^2 = p - p^2 = p\cdot(1-p) = p\cdot q $$


