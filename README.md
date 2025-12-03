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
Developed by: SOMESHWAR KUMAR 
RegisterNumber:  212224240157
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
## Data.head()
<img width="787" height="161" alt="image" src="https://github.com/user-attachments/assets/d59c8068-b01c-4b4b-b7cd-03a87da2ae47" />

## Data.info()
<img width="568" height="308" alt="image" src="https://github.com/user-attachments/assets/78f9dadc-0b69-492f-9d00-812a02e77f65" />


## Data isnull() sum()
<img width="330" height="199" alt="image" src="https://github.com/user-attachments/assets/b79ee541-b81d-4a20-9e80-e00df08b9dac" />

## Plot using elbow method:
<img width="945" height="661" alt="image" src="https://github.com/user-attachments/assets/5650693f-46c8-44c5-85d1-aaa7fcddbcb5" />

## Y_pred array
<img width="874" height="167" alt="image" src="https://github.com/user-attachments/assets/f6c4bc54-2284-47f8-945a-179b349e0c75" />

## Customer segment
<img width="920" height="668" alt="image" src="https://github.com/user-attachments/assets/9fb11099-e1cb-43a6-b722-62c710362c8d" />





## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
