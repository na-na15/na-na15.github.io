---
layout: post
title:      "Introduction to Supervised Learning in Machine Learning:"
date:       2020-11-06 04:13:28 -0500
permalink:  introduction_to_supervised_learning_in_machine_learning
---



When I started learning Machine Learning, I was found it confusing, especially when I want to use the many algorithms, techniques, and methods which are useful for different types of the datasets. How should I use them? So, I decided to put everything in order. First, let’s talk about what exactly ML does.

**What is Machine Learning?**

 Machine learning (ML) is the study of computer algorithms that improve automatically through experience. ML is a set of algorithms that classify or predict new data based on information obtained from a training set. In other words, we train the machine with our sample data then the machine classifies the new data based on the information gained. 
 
There are 4 types of the machine learning algorithms.

* 	Supervised Learning
* 	Unsupervised Learning
* 	Semi Supervised leaning
* 	Reinforcement Learning

In this post I am going to talk about supervised learning and different types of algorithms and techniques that are used to solve problems. What is the Supervised Learning?

The Supervised works based on the input and output variables. In Supervised learning we use the algorithm to learn the mapping function from the input to the output variables. This algorithm has a target variable which is to be predicted from a given set of other independent variables.  Supervised Learning is divided in two group based on the target variables. 

* **Regression:** The target variable is continuing.
The goal in the regression is to predict the target value. There many types of the regression, in the list below are the names of some of them.

 1. Linear Regression
 1. Multilinear Regression
 1. Polynomial Regression
 1. Ridge Regression
 1. Lasson Regression
 1. Elastic Net Regression

*	**Classification:** The target variable is categorical. 
Classification is a predictive modeling problem where a class label is predicted for testing data. There are 4 main types of the classification.

   1.Binary Classification: It refers to those classification tasks that the target variable has two class labels. Popular algorithms that can be used are:

   *	 Logistic Regression
   *	 K-Nearest Neighbors
   *	 Decision Trees
   *	 Support Vector Machine
   *	 Naive Bayes
  
  2 .Multi Classification: It refers to those classification tasks that the target variable has more than two class labels. In the list below some of the popular algorithms are coming.
 
   *	 K-Nearest Neighbors
   *	 Decision Trees
   *	 Naive Bayes
   *	 Random Forest
   *	 Gradient Boosting

   The binary classification algorithms can be used for multi-class problems. To do so, we need to fit multiple binary classification models. We have two options, first option is to fit one model for each class vs. all other classes, second option is to fit one model for each class vs. every other class separately.

  *	One-vs-Rest: Fit one binary classification model for each class vs. all other classes.
  *	One-vs-One: Fit one binary classification model for each pair of classes.

  Binary classification algorithms that can use these strategies for multi-class classification include:

  * Logistic Regression.
  *	Support Vector Machine.

  3 .Multi Label Classification: It refers to those classification tasks that the target variable has two or more class labels, and maybe for one sample more than one class label is predicted.
 
  *	Multi-label Decision Trees
  *	Multi-label Random Forests
  *	Multi-label Gradient Boosting
 
   Classification algorithms used for binary or multi-class classification cannot be used directly for multi-label classification. Specialized versions of standard classification algorithms can be used.

  4 .Imbalanced Classification: It refers to classification tasks where the number of examples in each target variable labels are unequal.
 
  *	Cost-sensitive Logistic Regression.
  *	Cost-sensitive Decision Trees.
  *	Cost-sensitive Support Vector Machines.
 
Under sampling the majority class or oversampling the minority class in the training data are two ways that are used to change the composition of samples. Here, Listed below, are examples of specialized techniques for under sampling and oversampling.

 *	 Random Under sampling.
 *	 SMOTE Oversampling.

[\[1\]](https://www.researchgate.net/profile/Zbigniew_Leonowicz/publication/321543275/figure/fig2/AS:649660200910856@1531902470662/Types-of-Machine-Learning-Algorithm.png)



     


    



