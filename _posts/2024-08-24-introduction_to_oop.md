---
title: "Introduction to OOP by Corey Schafer" 
date: 2024-08-22 00:19:00 
categories: [Python Programming]
tags: [Python]
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

# Introduction to OOP by Corey Schafer in Python

### Introduction

The first question one may ask is : "Why should we use OOP in python?" 

OOP allow us to logically group our data and functions in a way that's easy to reuse and also easy to build upon if need be.

So, let's start with a practical example:

Say we had an application for our company and wewanted to represent our employees ; this would be a great use case for a class because each individual employee is going to have specific attributes and methods, so for example each employee is going to have: - a name ; - an email address ; - a pay and also some other attributes that they might have.

A class can solve this problem, by serving as a blueprint to create each employee so that we didn't have to manually do it each time from scratch.

### Classes and Instances (Video 1)

A class is basically a blueprint for creating instances , in our example , each unique employee will be an instance of our class , thereby each object will have an unique storage location in memory.

<script src="https://gist.github.com/alexandregsg/10cf0bf4cba77917d6a7cd4f4acd8e88.js"></script>

#### Methods within a class

If we want to perform some kind of action in our class, we can add some so called methods.

<script src="https://gist.github.com/alexandregsg/1600c4dd348c3f16558c16de374458b0.js"></script>


### Class Variables (Video 2)

While Instance Variables, can be unique for each instance (ex: the name can differ from instance to instance) ; Class Variables should be the same for each instance.

If we want to set a pay raise to our employees, even tho the absolute amount can differ from employee to employee, we can set a Class variable to set up the same % amount.

The first approach we can think of to apply a raise is the following:

<script src="https://gist.github.com/alexandregsg/205988bd9489aaceb3173713fa5689a0.js"></script>

Nevertheless, there's a better way to update the value of the raise at any moment, and to access it easily:

<script src="https://gist.github.com/alexandregsg/5602094a6b894579101d3694e74c934e.js"></script>


### Class methods (Video 3)

<script src="https://gist.github.com/alexandregsg/2937f97d76b6bf62da9b5c0761006f66.js"></script>

### Static Methods (Video 3)

When working with classes, regular methods automatically pass the instance as the first argument and we call that "self" , and class methods pass the class as the first argument and we call that "cls".

Static methods don't pass anything automatically, they don't pass the instance or the class, so really they behave just like regular functions except we include them in our classes because they have some logical conection with the class , but it doesn't actually depend on any specifical instance or class variable.


<script src="https://gist.github.com/alexandregsg/bf20980b4a220570a6e465b711efee48.js"></script>

We should use static methods if we don't access the instance or the class anywhere within the function. In the from_string method , we used the cls variable but if we didn't , probably it didn't need to be a class method. The same applies to regular methods, if we are not using the self variable probably we should use a static method in that place.


