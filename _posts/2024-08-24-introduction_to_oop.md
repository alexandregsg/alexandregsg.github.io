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
