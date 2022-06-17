# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: DHARSHINI D.S
RegisterNumber: 212221230022 
*/
```
```
#import packages
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans (n_clusters = i, init ="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:

Dataset:

![ML7](https://user-images.githubusercontent.com/93427345/174313462-6dd142d0-5921-4ecd-ae49-70e3542b8e69.PNG)

Dataset information:

![Ml71](https://user-images.githubusercontent.com/93427345/174313500-dae54e5d-1d72-4a69-85a2-e29cc924d2bf.PNG)

![ml72](https://user-images.githubusercontent.com/93427345/174313612-2f445355-1116-4ec9-b7ad-2dcee9005b95.PNG)

Elbow method graph (wcss vs each iteration):

![ml73](https://user-images.githubusercontent.com/93427345/174313560-3e7ceeea-29ab-42b2-94aa-2054f302fa57.PNG)

Cluster represnting customer segments-graph:

![ml74](https://user-images.githubusercontent.com/93427345/174313651-ad929e4f-5861-4921-8aa7-7325e331bedb.PNG)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
