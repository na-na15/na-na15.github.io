---
layout: post
title:      " Knowladge Tracing "
date:       2021-01-10 16:09:27 -0500
permalink:  knowladge_tracing
---


In this blog post I am going to talk about how we can create a model to track a student’s knowledge. Before I start to talk about the model, let’s briefly look at what is knowledge tracing and why it is important and how it can help students or any person who wants to learn new things. 

In the traditional education systems normally teachers or instructors monitor and assess student’s knowledge based on their skills and abilities. In case students need more help or practice, their teachers would assist them. Imagining the situation that each student can trace her/his knowledge. In other words, the knowledge has been separated in a different level of skills, and the sequences of learning activities help leaning progress. Now, each student can obtain requirement skills based on her/his knowledge and abilities before moving to the next complex topic. In this way, students just spend their time to improve their weakness and get more attendance, engagement and individualized attention. Therefore, in modifying what student’s need in their next steps for learning, it is necessary to track, measure, and predict student’s changing knowledge, state, thereby personalizing the design. For having the more effective automated tutoring systems the student’s knowledge state should be modeled which is called knowledge tracing and replace the traditional ways that instructors use to assess the students’ performance with sequence of formative and summative learning activities. In knowledge tracing, machine learning algorithms help us to model student performance which has a high educational impact on automated tutoring systems.

There is a new Transformer_based model for knowledge tracing, that I am going to talk about here. 
SAINT(Separated Self-AttentIve Neural Knowledge Tracing) has an encoder_decoder structure. For having a better understanding of encoder_decoder structure let’s look at an example. Imagen we have two interpreters. One of them knows the French and the other one knows German, and  both of them are  familiar with a secret language. So for translating a sentence from French to German we should first translate the sentence into a secret language, and then translate it from secret language into German.  The action of translating the French into the secret language is called encoding and the action of translating the secret language into Germany is called decoding.  Now we have an idea what is the encoding and decoding. So the overall of encoder-decoder (sequence to sequence) is as shown below.

![](https://miro.medium.com/max/1250/1*zq1G3mPSuy-KoMlBldohww.png)

In the SAINT model,  the exercise sequences and response sequence  are separated then they are  applied  to encoder and decoder, respectively, which causes SAINT to capture  the complex relations among exercises and responses through deep self-attentive computations.


![](https://d3i71xaburhd42.cloudfront.net/255f0fe65f5592659c285a1ecb733dec57aada23/2-Figure2-1.png)

