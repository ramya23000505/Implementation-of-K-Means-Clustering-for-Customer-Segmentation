# Implementation-of-K-Means-Clustering-for-Customer-Segmentation
### Date:
## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Start the Program.

 2.Import dataset and print head,info of the dataset.

3.check for null values.

4.Import kmeans and fit it to the dataset.

5.Plot the graph using elbow method.

6.Print the predicted array.

7.Plot the customer segments.

8.End the program.
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Ramya R
RegisterNumber: 21223230169

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv('Exp_9_Mall_Customers.csv')

data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss =[] #Within-cluster Sum pof Square.
#It is the sum of Squared distance between each point & the centroid in the cluster

for i in range(1,11):
    kmeans=KMeans(n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km = KMeans(n_clusters =5)
km.fit(data.iloc[:,3:])

KMeans(n_clusters=5)

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
plt.title("Customer Segments")
*/
```

## Output:
### Elbow Method:
![Screenshot 2024-09-30 111016](https://github.com/user-attachments/assets/78ad2e33-4c40-4ffe-8465-fdeaf5328d57)

### Y-Predict:
![Screenshot 2024-09-30 111025](https://github.com/user-attachments/assets/2fb1d32f-4857-4bd3-9b82-d3dad150a99c)

### Customer Segments:
![Screenshot 2024-09-30 111032](https://github.com/user-attachments/assets/7a1c0ecc-66d5-4060-8b8b-56102a158c96)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
