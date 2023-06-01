# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print head,info of the dataset
2. check for null values
3. Import kmeans and fit it to the dataset
4. Plot the graph using elbow method
5. Print the predicted array
6. Plot the customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Manjupriya P
RegisterNumber: 212220220024
*/
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


## Output:
1.DATA.HEAD():

![image](https://github.com/Manjupriya1207/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113583090/8a66a27d-1b00-47ee-bd99-0ea50a384a3a)

2.DATA.INF0():

![image](https://github.com/Manjupriya1207/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113583090/a4585c94-0544-4e96-b066-56f8e2838565)

3.DATA.ISNULL().SUM():

![image](https://github.com/Manjupriya1207/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113583090/5a9f35d6-85fb-4274-9829-ce27e1588d04)

4.PLOT USING ELBOW METHOD:

![image](https://github.com/Manjupriya1207/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113583090/5330b598-6253-418b-9012-d9e3930e58f9)

5.K-MEANS CLUSTERING:

![image](https://github.com/Manjupriya1207/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113583090/87f34e3c-6208-4b76-af9c-1e4aa02d698d)

6.Y_PRED ARRAY:

![image](https://github.com/Manjupriya1207/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113583090/db6afae1-8b6e-44f9-aed7-b67fca01e187)

7.CUSTOMER SEGMENT:

![image](https://github.com/Manjupriya1207/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113583090/67fa81d3-5c96-4390-85d7-627356d8a19b)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
