# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset
2.check for null values
3.Import kmeans and fit it to the dataset
4.Plot the graph using elbow method
5.Print the predicted array
6.Plot the customer segments
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: A.DIVIYADHARSHINI
RegisterNumber:  212224040080
*/
```
```
import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")
```

## Output:

1.DATA.HEAD():

<img width="722" height="246" alt="image" src="https://github.com/user-attachments/assets/9a61d46c-3bdd-42b2-a3dd-19b081626f9c" />

2.DATA.INF0():

<img width="673" height="331" alt="image" src="https://github.com/user-attachments/assets/2b987351-a0ca-4bf0-94b2-711570913e19" />

3.DATA.ISNULL().SUM():

<img width="421" height="178" alt="image" src="https://github.com/user-attachments/assets/4238aea6-435c-493d-a207-0dd1ef69c3a7" />

4.PLOT USING ELBOW METHOD:

<img width="1035" height="720" alt="image" src="https://github.com/user-attachments/assets/d5bf9451-499f-4b8d-92a2-fc977d6e189e" />

5.K-MEANS CLUSTERING:

<img width="894" height="280" alt="image" src="https://github.com/user-attachments/assets/945fe2e3-f2fb-4580-8c4c-62fc3ba87a84" />

6.Y_PRED ARRAY:

<img width="845" height="260" alt="image" src="https://github.com/user-attachments/assets/49bcf8e5-043b-490a-b1a9-734f70bcf912" />

7.CUSTOMER SEGMENT:

<img width="879" height="661" alt="image" src="https://github.com/user-attachments/assets/2a386eb4-ba4e-45b6-8ab2-699db415727f" />











## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
