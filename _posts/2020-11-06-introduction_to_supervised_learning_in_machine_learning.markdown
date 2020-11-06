---
layout: post
title:      "Introduction to Supervised Learning in Machine Learning:"
date:       2020-11-06 09:13:27 +0000
permalink:  introduction_to_supervised_learning_in_machine_learning
---



When I started learning Machine Learning, I was confusing, especially when I wanted to use different ML algorithms. There are many algorithms, techniques, and methods which are useful for different types of data. I wasn’t sure how should I use them. So, I decided to organize everything I have learned. First, let’s talk about what exactly ML is.

**What is Machine Learning?**

Machine Learning (ML) is the study of computer algorithms that improve automatically through experience. ML is a set of algorithms that classify or predict new data based on information obtained from training set. In other words, we train the machine with our sample data then the machine predicts or classifies the new data based on the information gained in the training phase. 

There are 4 types of the Machine Learning algorithms.

*	Supervised learning
*	Unsupervised learning
*	Semi Supervised leaning
* Reinforcement learning

In this post I am going to talk about supervised learning and different types of algorithms and techniques that are used to solve problems.

**What is Supervised Learning? **

Supervised learning works based on the input and output variables. In supervised learning we use the algorithm to learn the mapping function from the input to the output variables. These algorithms have a target variable  which is to be predicted based on given set of other independent variables.  Supervised learning is divided in two group based on the type of target variables.

* Continuous target variables: regression. There are many types of the regression algorithms, below is the list of some of these algorithms.
 1. *Linear Regression*
 2. *Multilinear Regression*
 3. *Polynomial Regression*
 4. *Ridge Regression*
 5. *Lasson Regression*
 6. *Elastic Net Regression*

* Categorical target variable: classification. There are 4 main types of classification. 
 1. *Binary Classification:* 
 It refers to those classification  that the target variable has two class labels. Popular algorithms that can be use : 
    *	Logistic Regression
    *	K-Nearest Neighbors
    * Decision Trees
    *	Support Vector Machine
    * Naive Bayes

 2. *Multi class Classification:*
 It refers to those classification tasks that the target variable has more than two class labels. Below is a list of some of the popular algorithms.
     * K-Nearest Neighbors
     *	Decision Trees
     *	Naive Bayes 
     *	Random Forest
     *	Gradient Boosting

    Binary classification algorithms can be used for multi-class Classification. To do so, we need to fit multiple binary       classification models. We have two options, first option is to fit one model for each class vs. all other classes combined, second option is to fit one model for each class vs. every other class separately.
     
       *	 One-vs-Rest: Fit one binary classification model for each class vs. all other classes.
       *	 One-vs-One: Fit one binary classification model for each pair of classes.
	
    Binary classification algorithms that can use these strategies for multi-class classification include:
      *	Logistic Regression.
      * Support Vector Machine.

 3. *Multi Label Classification:* 
 It refers to those classification that the target variable has two or more class labels, and maybe for one sample more than one class label is predicted.
 
    *	 Multi-label Decision Trees
    *	 Multi-label Random Forests
    *	 Multi-label Gradient Boosting
    
    Classification  algorithms used for binary or multi-class classifications cannot be used directly for multi-label classification. Specialized versions of standard classification algorithms can be used.
		
 4. *Imbalanced Classification:*
   It refers to classification tasks where the number of examples in each target variable labels are unequal.
	   * Cost-sensitive Logistic Regression.
	   * Cost-sensitive Decision Trees.
	   * Cost-sensitive Support Vector Machines.
	   
	Undersampling the majority class or oversampling the minority class in the training data are two ways that are used to change the composition of samples in Imbalanced data. Here, example of specialized techniques for under sampling and oversampling.
     * 	Random Under sampling.
     *   SMOTE Oversampling.




     


    



