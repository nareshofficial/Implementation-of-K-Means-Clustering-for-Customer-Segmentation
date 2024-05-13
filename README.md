# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
Hardware – PCs
Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import pandas and matplotlib.pyplot.
2.Read the dataset and transform it.
3.Import KMeans and fit the data in the model.
4.Plot the Cluster graph.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: NARESH.PS
RegisterNumber: 212223040127
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square. 
for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:

### data.head() 
![image](https://github.com/Loshini2301/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150007305/1b5306e7-a3ae-4df7-b625-135d10b2816f)

### data.info()
![image](https://github.com/Loshini2301/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150007305/306d2217-1034-4661-9ecc-87d1c15221f3)

### data.isnull().sum() 
![image](https://github.com/Loshini2301/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150007305/a68b11b8-294a-4c0e-b43b-d137397b24a1)

### Elbow method Graph
![image](https://github.com/Loshini2301/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150007305/0b1c3718-b07a-4b73-b1ff-93aad6f44a32)

### KMeans clusters
![image](https://github.com/Loshini2301/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150007305/f0f4c9c0-b411-4ca6-be72-0666a006fc9b)
![image](https://github.com/Loshini2301/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150007305/e36c6f94-fdff-41f4-816f-8616a636f97b)

### Customer segments Graph
![image](https://github.com/Loshini2301/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150007305/f66fb993-9b27-4ea5-886f-199680f1cf80)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
