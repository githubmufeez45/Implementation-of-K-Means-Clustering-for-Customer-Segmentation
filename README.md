# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SOUVIK KUNDU
RegisterNumber: 212221230105
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
# dataset:
![278795578-afbcb3f0-41a0-4e9e-bafd-a0fafb3334c0](https://github.com/githubmufeez45/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/134826568/26692c13-adc7-4ba5-a88f-e17a0be00c3e)

# Dataset information:
![278795602-253e3aeb-6850-4bfd-b39b-9e82bf90d834](https://github.com/githubmufeez45/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/134826568/32d2ab01-d216-4fae-adbc-bbd51093212f)

![278795605-b654a77d-774e-4cc0-9396-4353a521f7cc](https://github.com/githubmufeez45/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/134826568/cee78d63-cfcf-4da1-a7fb-0de5a20e7a2f)

# Elbow method graph (wcss vs each iteration):
![278795631-c7b3a69a-089c-4ff3-b253-9a2a0b6e0daa](https://github.com/githubmufeez45/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/134826568/ca6ed196-036e-411e-b2bb-0ed2def5d058)

# Cluster represnting customer segments-graph:
![278795641-c898bcee-13f7-49d2-918c-dc151a9702f3](https://github.com/githubmufeez45/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/134826568/03319e3b-b15e-4d25-a9ac-e4ce4ea7eb89)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
