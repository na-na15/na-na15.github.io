---
layout: post
title:      " Knowladge Tracing "
date:       2021-01-10 16:09:27 -0500
permalink:  knowladge_tracing
---


In this blog post I am going to talk about how we can create a model to track a student’s knowledge. Before I start to talk about the model, let’s briefly look at what is knowledge tracing and why it is important and how it can help students or any person who wants to learn new things. 

In the traditional education systems normally teachers or instructors monitor and assess student’s knowledge based on their skills and abilities. In case students need more help or practice, their teachers would assist them. Imagining the situation that each student can trace her/his knowledge. In other words, the knowledge has been separated in a different level of skills, and the sequences of learning activities help leaning progress. Now, each student can obtain requirement skills based on her/his knowledge and abilities before moving to the next complex topic. In this way, students just spend their time to improve their weakness and get more attendance, engagement and individualized attention. Therefore, in modifying what student’s need in their next steps for learning, it is necessary to track, measure, and predict student’s changing knowledge, state, thereby personalizing the design. For having the more effective automated tutoring systems the student’s knowledge state should be modeled which is called knowledge tracing and replace the traditional ways that instructors use to assess the students’ performance with sequence of formative and summative learning activities. In knowledge tracing, machine learning algorithms help us to model student performance which has a high educational impact on automated tutoring systems.

There is a new Transformer_based model for knowledge tracing, that I am going to talk about here. SAINT(Separated Self-AttentIve Neural Knowledge Tracing) has an encoder_decoder structure. For having a better understanding of encoder_decoder structure let’s look at an example. Imagen we have a translator machine, which takes an English sentence and transforms it to German. 

<img align="right"src="https://lionbridge.ai/wp-content/uploads/2020/09/1.png" alt="drawing" width="99%"/>




A transformer is essentially a stack of encoder and decoder layers. 

<img align="right" src="https://miro.medium.com/max/1250/1*zq1G3mPSuy-KoMlBldohww.png"width="130%"/>


the encoder in the picture, convert the English sentence into secret language(which is numerical form ), and the decoder convert the secret language into German. So the encoder converts the input sequence(in our example a sentence in English ) into a single dimensional hidden vector (the secret language), and the decoder converts the hidden vector into the output sequence. Encoder-Decoder models are jointly trained to maximize the conditional probabilities of the target sequence given the input sequence. 


Let's look at how the encoder and decoder work. The encoder stack contains the several encode layers on top of each other. Each encode stack has two essential layers:

* A multi-head self-attention Layer
* A position-wise fully connected feed-forward network


The decoder stack has several layers and each decoder stack is comprised of the following three layers:

* Masked multi-head self-attention Layer
* Multi-head self-attention Layer
* A position-wise fully connected feed-forward network

<img align="center" src="http://jalammar.github.io/images/t/Transformer_decoder.png"width="99%"/>







