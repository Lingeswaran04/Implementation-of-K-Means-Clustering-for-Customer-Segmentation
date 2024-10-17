# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## EQUIPMENTS REQUIRED:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## ALGORITHM:
1. Import required libraries.
2. Read the data frame using pandas.
3. Get the information regarding the null values present in the dataframe.
4. Apply label encoder to the non-numerical column in order to convert into numerical values
5. Determine training and testing data set.
6. Apply k-means clustering for customer segmentation.

## PROGRAM:
### DATA SET
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: LINGESWARAN K
RegisterNumber:  212222110022
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head()
```
### INFO
```
data.info()
```
### DATA FRAME
```
data.isnull().sum()
```
### KMEANS CLUSTER
```
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans (n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
```
### PLOTTING
```
plt.plot(range (1,11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
```
### FIT
```
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
```
### PREDICT
```
y_pred = km.predict(data.iloc[:,3:])
y_pred
```
### CUSTOMER SEGMENTS
```
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"],c="red", label="cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"],c="black", label="cluster1")
plt.scatter(df2["Annual Income (k$)"], df2 ["Spending Score (1-100)"],c="blue", label="cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"],c="green", label="cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"],c="magenta", label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## OUTPUT:
### DATA SET
![image](https://github.com/user-attachments/assets/57e3f8e4-9816-48b8-bb29-2a343480b618)

### INFO
![image](https://github.com/user-attachments/assets/92f645da-802f-4e3b-a240-9d9a81be3bfe)

### DATA FRAME
![image](https://github.com/user-attachments/assets/a7f028ee-796a-447e-87ed-ef0f2403a76f)

### KMEANS CLUSTER
![image](https://github.com/user-attachments/assets/e457b7a9-be2d-44fa-9f04-e575352e3adf)

### PLOTTING
![image](https://github.com/user-attachments/assets/cd7b9118-672b-438a-80b4-8c7baf0f0eeb)

### FIT

![image](https://github.com/user-attachments/assets/6d258db8-6397-42ad-8120-d7a77176cff6)

### PREDICT
![image](https://github.com/user-attachments/assets/c7df6937-6722-4d4c-bff5-3d166ae2849b)


### CUSTOMER SEGMENTS
![image](https://github.com/user-attachments/assets/52b712d5-4c60-48f0-9e80-b6bb617feb36)



## RESULT:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
