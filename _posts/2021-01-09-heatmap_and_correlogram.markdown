---
layout: post
title:      "HeatMap & Correlogram:"
date:       2021-01-09 08:15:55 +0000
permalink:  heatmap_and_correlogram
---


###  Introduction :
In this post I am going to briefly talk about correlograms.  Correlograms are a convenient  way to show the relation between numeric variables. Using the different shades of colors in diagrams help users to have better understanding of the relation among the variables. Before I start to talk about correlograms, let’s talk about Heatmap. Correlogram is a variant of the heatmap that replaces each of the variables on the two axes with a list of numeric variables in the dataset. [\[1\]](https://chartio.com/learn/charts/heatmap-complete-guide/)

### What is Heatmap? 
Aheatmap is a 2_dimensional graph which represents values for a variable across two axis variables as a grid and colored each square. In other words, it is like a colorful data frame. It is useful to display  a general view of numerical data.[\[3\]](https://blog.quantinsti.com/creating-heatmap-using-python-seaborn/#:~:text=A%20heatmap%20is%20a%20two,Annotated%20Heatmap)

### When should we use heatmap?
Normally for representing the relationships between two categorical variables or several numeric variables, heatmap can be a good choice. Let's look at an example for categorical variables.  In this plot the axis are  categorical variables, one is months and another one is years. 

```

>>Input:
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
import seaborn as sns
plt.rcParams['figure.figsize'] = (10, 8)
plt.rcParams['font.family'] = "serif"

```



```

>>Input:
flights = sns.load_dataset("flights")
flights = flights.pivot(index = "month", columns = "year", values = "passengers")

```


```
>>Input
ax = sns.heatmap(flights, annot=True, fmt="d",linewidths=.5,annot_kws={'size':10})
plt.xlabel('Month')
plt.ylabel('Year')
ax.set_ylim((0,10))
plt.text(5,11, "Heat Map", fontsize = 16, color='Black', fontstyle='italic')

```

![](https://lh6.googleusercontent.com/Nr_ZNoDKbsirW75fSLGVO-DqnQ4_u9YOG13U3GSued2TpUIX9gaKqrFhsVY9ekhqR9W7b4Hszxx8zZPyF9az=w3272-h1896)


Based on the graph above by passing the time the number of the flights are increased, and in July and August we have the highest number of passengers. 


In this part I am going to walk through when each of the categorical variables in the axis are replaced with a list of numeric variables in the dataset. Each square shows the relation between the  intersecting variables.  This  heatmap is called corrologram. Let’s look at an example. 

```

>>Input:
data = {'A': [45,37,42,35,39,38,41],
        'B': [38,31,26,28,33,25,30],
        'C': [10,15,17,21,12,19,22],
        'D': [65,54,60,58,62,50,59],
        'E': [18,13,15,19,10,17,]
        }

df = pd.DataFrame(data,columns=['A','B','C','D','E'])

corrMatrix = df.corr()

plt.rcParams['figure.figsize'] = (8, 6)
plt.rcParams['font.family'] = "serif"
sns.heatmap(corrMatrix, annot=True, linewidths=.5,annot_kws={'size':16})
plt.show()

```
![](https://lh6.googleusercontent.com/Fk3bETLL9BbmvYUn8lgGyvF7LQywjAaUnLEOrorLqQ18E96S55nD2tcQgSmHsqpk6J4XRYYuwRoKD04NZmYr=w3272-h1214)

Use a mask to plot only part of a matrix

```
>>Input:
mask = np.zeros_like(corrMatrix)
mask[np.triu_indices_from(mask)] = True
with sns.axes_style("white"):
    f, ax = plt.subplots(figsize=(8, 6))
    ax = sns.heatmap(corrMatrix, mask=mask, vmax=.3, square=True, annot=True)
```

![](https://lh6.googleusercontent.com/zlpUzJFQST9jizXtcpCmhFKTEVSv0H8GntfVeVfxIZ1BoUCkC3rmt87_BF8wHBWjFs0mb4JYoCi_L7d-aiOe=w3272-h1214)
### Sources:
[\[1\]A Complete Guide to Heatmaps](https://chartio.com/learn/charts/heatmap-complete-guide/)

[\[2\]seaborn.heatmap](http://alanpryorjr.com/visualizations/seaborn/heatmap/heatmap/)

[\[3\]Creating Heatmap Using Python Seaborn ](https://blog.quantinsti.com/creating-heatmap-using-python-seaborn/#:~:text=A%20heatmap%20is%20a%20two,Annotated%20Heatmap)
