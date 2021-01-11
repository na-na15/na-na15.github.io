---
layout: post
title:      "Embedding in ML:"
date:       2021-01-11 22:00:25 +0000
permalink:  embedding_in_ml
---


Have you ever been in that situation where your dataset has a lot of categorical variables and you try to create a model. One of the solutions is using Hot Encoding. In One_Hot Encoding each categorical column is splitted to many columns depending on the number of categories present in the column. Each column is mapped with 0 or 1s. Normally 1 represents  an action that happened and 0 represents the action that did not happen.

![](https://cdn.analyticsvidhya.com/wp-content/uploads/2020/08/Screenshot-from-2020-08-12-17-16-03-850x322.png)


The disadvantage is that for high cardinality, the feature space can really blow up quickly and you start fighting with the curse of dimensionality. In these cases, I typically employ one-hot-encoding followed by PCA for dimensionality reduction. 

There is another concept for vector representation in deep learning especially in Natural Language  Processing, which is called Embedding. In the context of machine learning, an embedding is a low-dimensional, learned continuous vector representation of discrete variables into which you can translate high-dimensional vectors. Generally, embeddings make ML models more efficient and easier to work with, and can be used with other models as well.


One of the uses of Embedding is in neural networks. There are 3main purposes for embedding in neural networks.

* Finding nearest neighbors in the embedding space. These can be used to make recommendations based on user interests or cluster categories
* As input to a machine learning model for a supervised task.
* For visualization of concepts and relations between categories.

### Build a simple embedding network with keras
The Keras library is one of the most famous and commonly used deep learning libraries for Python that is built on top of TensorFlow. In this section we will see how embeddings are used with Keras Sequential API.

```
>>Input

#import the libraries
from keras.models import Sequential
from keras.layers import Embedding, Flatten, Dense, Activation
from keras.optimizers import SGD
```

```
>>Input 

n_categories = 3  # number of possible categories
emb_dim = 5       # dimension of the emdedding vectors

```
```
>>Input

#Create neural network
model = Sequential()
model.add(Embedding(input_dim=n_categories, output_dim=emb_dim, input_shape=(1,)))
model.add(Flatten())
model.add(Dense(units=1, activation="sigmoid"))

```

```
>>Input

sgd = SGD(lr=learning_rate)
model.compile(optimizer=sgd, loss="binary_crossentropy", metrics=["accuracy"])

```
The reason we use argmax to get the category index is that the keras can manage the one_hot encoding internally, therefore we have to pass integer indices for our categories.

```
>>Input
 #Fit the model
 model.fit(np.argmax(X, axis=1), y, epochs=5);

```

```
>>Output

Epoch 1/5
4/4 [==============================] - 0s 44ms/step - loss: 0.7012 - acc: 0.5000
Epoch 2/5
4/4 [==============================] - 0s 633us/step - loss: 0.6838 - acc: 0.5000
Epoch 3/5
4/4 [==============================] - 0s 300us/step - loss: 0.6670 - acc: 1.0000
Epoch 4/5
4/4 [==============================] - 0s 507us/step - loss: 0.6509 - acc: 1.0000
Epoch 5/5
4/4 [==============================] - 0s 3ms/step - loss: 0.6352 - acc: 1.0000

```

```
>>Input

keras_embs = model.layers[0].get_weights()[0]
keras_embs

```

```
>>Output

array([[ 0.02557688,  0.03779284, -0.05189876,  0.06510007, -0.03094837],
       [ 0.00011533,  0.05283174, -0.05359174,  0.03876735, -0.06703786],
       [-0.00463526, -0.0850474 ,  0.07373089, -0.02540122,  0.07149601]],
      dtype=float32)


```






