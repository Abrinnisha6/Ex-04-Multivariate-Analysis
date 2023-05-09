# Ex-04-Multivariate-Analysis

## AIM :

To perform Multivariate EDA on the given data set.

## EXPLANATION :

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM :

## STEP 1 :

Import the built libraries required to perform EDA and outlier removal.

## STEP 2 :

Read the given csv file.

## STEP 3 :

Convert the file into a dataframe and get information of the data.

## STEP 4 :

Return the objects containing counts of unique values using (value_counts()).

## STEP 5 :

Plot the counts in the form of Histogram or Bar Graph.

## STEP 6 :

Use seaborn the bar graph comparison of data can be viewed.

## STEP 7 :

Find the pairwise correlation of all columns in the dataframe.corr() .

## STEP 8 :

Save the final data set into the file.

## Program : 

```import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.dtypes

data.isnull().sum()

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Sales'],data=data)

states=data.loc[:,["Region","Sales"]] 
states=states.groupby(by=["Region"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("REGION")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SALES") 
plt.ylabel=("STATES") 
plt.show()

states=data.loc[:,["Category","Sales"]] 
states=states.groupby(by=["Category"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("CATEGORY") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
```

## OUTPUT :

## DATASET :

![](o1.png)

## HEAD() :

![](o2.png)

## INFO() :

![](o3.png)

## DESCRIBE() :

![](o4.png)

## DATATYPE() :

![](o5.png)

## ISNULL() :

![](o6.png)

## Postal code has outliers :

![](o7.png)

## After removing outliers from Postal Code :

## MULTIVARIATE ANALYSIS :

## SCATTER PLOT :

![](o8.png)

## BARPLOT :

![](o9.png)

![](o10.png)

## SEGMENTATION :

![](o11.png)

## CORRESSION :

![](o13.png)

## HEATMAP() :

![](o12.png)

## RESULT :

Hence The Performance of the Multivariate EDA on the given data set is verified.
