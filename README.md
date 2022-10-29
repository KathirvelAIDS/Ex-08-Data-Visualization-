# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.

~~~
NAME:KATHIRVEL.A
REG NO:212221230047
~~~


~~~
import pandas as pd
import numpy as np
df=pd.read_csv("Superstore.csv")

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

#4.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#5.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#6.Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

#7.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#8.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()              

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()


~~~


OUTPUT:


![image](https://user-images.githubusercontent.com/94911373/198820193-05cf5e2a-bc20-4bb9-bcb2-5a7eda1e9f1b.png)



![image](https://user-images.githubusercontent.com/94911373/198820217-a25c61c7-7967-4975-abd1-9a4e7f4d5f64.png)



![image](https://user-images.githubusercontent.com/94911373/198820220-47b868d6-6e65-4b9c-aadb-e710d2e8ddae.png)


![image](https://user-images.githubusercontent.com/94911373/198820236-5d2fa391-af27-462a-9dbb-0b1b18ada979.png)



![image](https://user-images.githubusercontent.com/94911373/198820244-cc052953-e0e9-4940-a0a0-69e66675bee1.png)



![image](https://user-images.githubusercontent.com/94911373/198820252-1fd092fa-1fad-42b1-998f-0686675f0a1b.png)



![image](https://user-images.githubusercontent.com/94911373/198820256-f874a8ea-72b2-42c0-986b-958c4bd3cce4.png)


![image](https://user-images.githubusercontent.com/94911373/198820261-8fbd2270-6987-4094-a112-fe5182498f56.png)



![image](https://user-images.githubusercontent.com/94911373/198820267-611695d7-4ce6-4a15-b04f-6971106887b3.png)



![image](https://user-images.githubusercontent.com/94911373/198820272-a1f3cfc0-fca1-470a-b16e-81a20a0763ae.png)



![image](https://user-images.githubusercontent.com/94911373/198820277-470dd12c-a95c-49fd-ac9c-fad8b8f7da31.png)


![image](https://user-images.githubusercontent.com/94911373/198820287-a4c50fed-b778-48f2-a00d-71442c85f847.png)


![image](https://user-images.githubusercontent.com/94911373/198820292-eba99bb2-2d50-495d-ba5f-bb98f0fa277d.png)


![image](https://user-images.githubusercontent.com/94911373/198820296-095936b8-eee0-46e2-9c4e-fe394f7721f7.png)


![image](https://user-images.githubusercontent.com/94911373/198820305-586a4edc-60fd-4479-ad11-57e648565d7b.png)


![image](https://user-images.githubusercontent.com/94911373/198820309-30dd252f-81f7-4e67-9599-9e6428993c8a.png)


![image](https://user-images.githubusercontent.com/94911373/198820315-545c2ee2-2099-4b5b-a41a-850475af229a.png)


![image](https://user-images.githubusercontent.com/94911373/198820323-f32ba462-bb86-46a9-b164-7a6cbcd64b8e.png)


![image](https://user-images.githubusercontent.com/94911373/198820327-81b50ae0-7fe0-4fe2-aa52-cfd3abd669ee.png)


![image](https://user-images.githubusercontent.com/94911373/198820337-71dcfaf7-60b5-435a-bec9-bfa1ba1773d7.png)


![image](https://user-images.githubusercontent.com/94911373/198820346-2450e555-5c44-472d-854f-eb57745ab89d.png)


![image](https://user-images.githubusercontent.com/94911373/198820350-6be79765-98e1-4dc0-8572-a39f8955259f.png)


![image](https://user-images.githubusercontent.com/94911373/198820356-691bc811-64e1-415a-bd84-3dcc01c19dd9.png)



![image](https://user-images.githubusercontent.com/94911373/198820364-b3519607-2786-47d8-a370-c8bfb8f641b6.png)


![image](https://user-images.githubusercontent.com/94911373/198820370-b9e5a9fd-8b07-4abb-ab80-f4f20c24aa88.png)




RESULT:

Hence, Data Visualization techniques is applied in the given dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file
