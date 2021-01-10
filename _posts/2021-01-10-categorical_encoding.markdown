---
layout: post
title:      "Categorical Encoding"
date:       2021-01-10 07:19:15 +0000
permalink:  categorical_encoding
---


Normally our data set is a combination of the numerical and categorical variables or columns. Since machines just can understand the numerical variables, how we can use the categorical variables in our models. For solving this problem, we should convert the categorical variables to the numbers. This process is called categorical encoding. There are several categorical encoding techniques. Here I am going to briefly talk about which Encoding techniques are appropriate when we have Ordinal  variables or nominal variables.  

### Ordinal Encoding or Label Encoding:

When the categorical feature is ordinal we can use ordinal Encoding. Since the order among the categories is important, encoding should reflect the sequence. For example, the categorical variable represents the education qualification of a person.  

```
>>Input
import category_encoders as ce
import pandas as pd
train_df=pd.DataFrame({'Degree':['High school','Masters','Diploma','Bachelors','Bachelors','Masters','Phd','High school','High school']})

# create object of Ordinalencoding
encoder= ce.OrdinalEncoder(cols=['Degree'],return_df=True,
                           mapping=[{'col':'Degree',
'mapping':{'None':0,'High school':1,'Diploma':2,'Bachelors':3,'Masters':4,'phd':5}}])

#Original data
train_df

```

![](https://cdn.analyticsvidhya.com/wp-content/uploads/2020/08/Screenshot-from-2020-08-12-14-49-12.png)

```
>>Input
#fit and transform train data 
df_train_transformed = encoder.fit_transform(train_df)

```
![](https://cdn.analyticsvidhya.com/wp-content/uploads/2020/08/Screenshot-from-2020-08-12-15-36-19.png)

### One Hot Encoding:

When the categorical features don’t have any order (nominal), we use the One_HotEncoding. 
In One_Hot Encoding each categorical column is splitted to many columns depending on the number of categories present in the column. Each column is mapped with 0 or 1s. Normally 1 represents  an action that happened and 0 represents the action that did not happen. For having a better understanding let’s look at an example.

![](https://cdn.analyticsvidhya.com/wp-content/uploads/2020/08/Screenshot-from-2020-08-12-17-16-03-850x322.png)

As you see in  the second table we have 5 columns that each of them represent of the categories(here the name of the animals) in the Animal columns.  Now for each category that is present, we have 1 in the column of that category and 0 for the others. Let’s look at how we can implement the second table

```
>>Input
import category_encoders as ce
import pandas as pd
data=pd.DataFrame({'City':[
'Delhi','Mumbai','Hydrabad','Chennai','Bangalore','Delhi','Hydrabad','Bangalore','Delhi'
]})

#Create object for one-hot encoding
encoder=ce.OneHotEncoder(cols='City',handle_unknown='return_nan',return_df=True,use_cat_names=True)

#Original Data
data

```
![](https://cdn.analyticsvidhya.com/wp-content/uploads/2020/08/Screenshot-from-2020-08-12-16-53-39.pnghttp://)

```
>>Input
#Fit and transform Data
data_encoded = encoder.fit_transform(data)
data_encoded

```
![](https://cdn.analyticsvidhya.com/wp-content/uploads/2020/08/Screenshot-from-2020-08-12-16-53-46-768x382.png)

### Endnote
Since encoding categorical variables is one of the tools which are used in most of the feature engineering, in this post, I tried to introduce and implement the two encoding techniques and the situation they can be used.




