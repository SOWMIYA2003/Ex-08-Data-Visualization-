# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

## Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


## CODE

```
Developed By: Sowmiya N.
Register No: 212221230106.
```
```
import pandas as pd
df=pd.read_csv("Superstore.csv")
df

#importing library
#Seaborn,Matplotlib - Python Library
import seaborn as sns
from matplotlib import pyplot as plt

#LINE PLOT

plt.figure(figsize=(8,5))
sns.lineplot(x="Sub-Category",y="Sales",data=df,marker='o')
plt.xticks(rotation = 90)

plt.figure(figsize=(8,5))
sns.lineplot(x="Category",y="Profit",data=df,marker='o')
plt.xticks(rotation = 90)

plt.figure(figsize=(8,5))
sns.lineplot(x="Region",y="Sales",data=df,marker='o')
plt.xticks(rotation = 90)

plt.figure(figsize=(8,5))
sns.lineplot(x="Sub-Category",y="Quantity",data=df,marker='o')
plt.xticks(rotation = 90)

sns.lineplot(x="Category",y="Discount",data=df,marker='o')

plt.figure(figsize=(12,7))
sns.lineplot(x="State",y="Sales",data=df,marker='o')
plt.xticks(rotation = 90)

#BAR PLOT

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.barplot(x="Category",y="Profit",data=df)

sns.barplot(x="Region",y="Sales",data=df)

sns.barplot(x="Sub-Category",y="Quantity",data=df)
plt.xticks(rotation = 90)

sns.barplot(x="Category",y="Discount",data=df)

plt.figure(figsize=(10,7))
sns.barplot(x="State",y="Sales",data=df)
plt.xticks(rotation = 90)

#HISTOGRAM

sns.histplot(data = df,x = 'Ship Mode',hue='Sub-Category')
sns.histplot(data = df,x = 'Region',hue='Ship Mode')
sns.histplot(data = df,x = 'Category',hue='Quantity')
sns.histplot(data = df,x = 'Sub-Category',hue='Category')
plt.xticks(rotation = 90)
plt.show()
sns.histplot(data = df,x = 'Quantity',hue='Segment')

plt.hist(data = df,x = 'Profit')
plt.hist(data = df,x = 'Discount')
plt.hist(data = df,x = 'Sales')
plt.hist(data = df,x = 'Quantity')

#SCATTER PLOT

sns.scatterplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.scatterplot(x="Category",y="Profit",data=df)

sns.scatterplot(x="Region",y="Sales",data=df)

sns.scatterplot(x="Sub-Category",y="Quantity",data=df)
plt.xticks(rotation = 90)

sns.scatterplot(x="Category",y="Discount",data=df)

plt.figure(figsize=(10,7))
sns.scatterplot(x="State",y="Sales",data=df)
plt.xticks(rotation = 90)

#BOX PLOT

plt.figure(figsize=(10,7))
sns.boxplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.boxplot(x="Category",y="Profit",data=df)
sns.boxplot(x="Region",y="Sales",data=states)

plt.figure(figsize=(10,7))
sns.boxplot(x="Sub-Category",y="Quantity",data=df)
plt.xticks(rotation = 90)

sns.boxplot(x="Category",y="Discount",data=df)

plt.figure(figsize=(15,7))
sns.boxplot(x="State",y="Sales",data=df)
plt.xticks(rotation = 90)

#COUNT PLOT

sns.countplot(x ='Ship Mode', data = df,hue = 'Quantity')
sns.countplot(x ='Segment', data = df,hue = 'Sub-Category')
sns.countplot(x ='Region', data = df,hue = 'Segment')
sns.countplot(x ='Category', data = df,hue='Discount')
sns.countplot(x ='Sub-Category', data = df,hue = 'Category')
plt.xticks(rotation = 90)

#KDE PLOT

sns.kdeplot(x="Profit", data = df,hue='Category')
sns.kdeplot(x="Sales", data = df,hue='Region')
sns.kdeplot(x="Discount", data = df,hue='Sub-Category')
sns.kdeplot(x="Quantity", data = df,hue='Segment')

#HEAT MAP


#Applying Ordinal Encoding to convert non-numeric data into numeric.

from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
oe=OrdinalEncoder()
oe.fit_transform(df[["Ship Mode"]])
Class=['Standard Class','Second Class','First Class','Same Day']
enc=OrdinalEncoder(categories=[Class])
enc
enc.fit_transform(df[['Ship Mode']])
df1=df.copy()
df1["Ship Mode"]=enc.fit_transform(df[["Ship Mode"]])
df1

oe1=OrdinalEncoder()
oe1.fit_transform(df1[["Segment"]])
Class=['Consumer','Corporate','Home Office']
enc1=OrdinalEncoder(categories=[Segment])
enc1
enc1.fit_transform(df1[['Segment']])
df2=df1.copy()
df2["Segment"]=enc1.fit_transform(df1[["Segment"]])
df2

oe2=OrdinalEncoder()
oe2.fit_transform(df2[["Region"]])
Region=['West','East','Central','South']
enc2=OrdinalEncoder(categories=[Region])
enc2
enc2.fit_transform(df2[['Region']])
df3=df2.copy()
df3["Region"]=enc2.fit_transform(df2[["Region"]])
df3

oe3=OrdinalEncoder()
oe3.fit_transform(df3[["Category"]])
Category=['Office Supplies','Furniture','Technology']
enc3=OrdinalEncoder(categories=[Category])
enc3
enc3.fit_transform(df3[['Category']])
df4=df3.copy()
df4["Category"]=enc3.fit_transform(df3[["Category"]])
df4

oe4=OrdinalEncoder()
oe4.fit_transform(df4[["Sub-Category"]])
SubCategory=['Binders','Paper','Furnishings','Phones',
'Storage','Art','Accessories','Chairs','Appliances',
'Labels','Tables','Envelopes','Bookcases'
,'Fasteners','Supplies','Machines','Copiers']
enc4=OrdinalEncoder(categories=[SubCategory])
enc4
enc4.fit_transform(df4[['Sub-Category']])
df5=df4.copy()
df5["Sub-Category"]=enc4.fit_transform(df4[["Sub-Category"]])
df5

#Applying Binary encoding 
from category_encoders import BinaryEncoder
be=BinaryEncoder()
newdata=be.fit_transform(df5["Country"])
newdata
df6=df5.copy()
df6["Country"]=be.fit_transform(df5[["Country"]])
df6

#Droping non-numeric columns from Dataset
df5.drop("Order ID",axis=1,inplace = True)
df5.drop("Order Date",axis=1,inplace = True)
df5.drop("Ship Date",axis=1,inplace = True)
df5.drop("Customer ID",axis=1,inplace = True)
df5.drop("Customer Name",axis=1,inplace = True)
df5.drop("City",axis=1,inplace = True)
df5.drop("Product ID",axis=1,inplace = True)
df5.drop("Product Name",axis=1,inplace = True)
df5.drop("State",axis=1,inplace = True)
df5

#Correlation of columns

df6.corr()
import seaborn as sns
from matplotlib import pyplot as plt
plt.subplots(figsize=(12,7))
sns.heatmap(df6.corr(),annot=True)

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
```
## OUPUT
### Initial DataFrame(Superstore.csv):
![op](./op/q1.png)
## LINE PLOT
### Sub-Category VS Sales:
![op](./op/q2.png)
### Category VS Profit:
![op](./op/q3.png)
### Region VS Sales:
![op](./op/q4.png)
### Sub-Category VS Quantity:
![op](./op/q5.png)
### Category VS Discount:
![op](./op/q6.png)
### State VS Sales:
![op](./op/q7.png)
## BAR GRAPH
### Sub-Category VS Sales:
![op](./op/q8.png)
### Category VS Profit:
![op](./op/q9.png)
### Region VS Sales:
![op](./op/q10.png)
### Sub-Category VS Quantity:
![op](./op/q11.png)
### Category VS Discount:
![op](./op/q12.png)
### State VS Sales:
![op](./op/q13.png)
## HISTOGRAM
### Ship Mode VS Sub-Category:
![op](./op/q14.png)
### Region VS Ship Mode:
![op](./op/q15.png)
### Category VS Quantity:
![op](./op/q16.png)
### Sub-Category VS Category:
![op](./op/q17.png)
### Quantity VS Segment:
![op](./op/q18.png)
## SCATTER PLOT
### Sub-Category VS Sales:
![op](./op/q23.png)
### Category VS Profit:
![op](./op/q24.png)
### Region VS Sales:
![op](./op/q25.png)
### Sub-Category VS Quantity:
![op](./op/q26.png)
### Category VS Discount:
![op](./op/q27.png) 
## BOX PLOT
### Sub-Category VS Sales:
![op](./op/q29.png)
### Category VS Profit:
![op](./op/q30.png)
### Region VS Sales:
![op](./op/q31.png)
### Sub-Category VS Quatity:
![op](./op/q32.png)
### Caterory VS Discount:
![op](./op/q33.png)
### State VS Sales:
![op](./op/q34.png)
## COUNT PLOT
### Ship Mode VS Quantity:
![op](./op/q35.png)
### Segment VS Sub-Category:
![op](./op/q36.png)
### Region VS Segment:
![op](./op/q37.png)
### Category VS Discount:
![op](./op/q38.png)
### Sub-Category VS Category:
![op](./op/q39.png)
## KDE PLOT
### Profit VS Category:
![op](./op/q40.png)
### Sales VS Region:
![op](./op/q41.png)
### Discount VS Sub-Category:
![op](./op/q42.png)
### Quantity VS Segment:
![op](./op/q43.png)
## HEAT MAP
## Applying Encoding Methods:

Enconding Methods such as Ordinal enconding and Binary encoding have been applied to the given data set inorder to convert the non-numerical data to numerical data.
Certain Non-numerical Columns (Order ID,Order Date,Ship Date,Customer ID,Customer Name,City,Product ID,Product Name,State.) have been removed from the data set inorder to produce the accurate heatmap.

### DataFrame After applying encoding methods and removal of certain columns:
![op](./op/q44.png)
### Correlation of columns:
![op](./op/q45.png)
### Graphical Representation to view correlation via HEAT MAP:
![op](./op/q46.png)

### Initial DataFrame - Without Applying Encoding Methods
### Correlation of columns in initial data frame:
```
Considers only numeric data that are present in the Dataframe.
```
![op](./op/q47.png)
### Graphical Representation to view correlation via HEAT MAP(Initial DataFrame):
![op](./op/q48.png)

## Inference(Insights) on DataSet:
```
1.The Overall sale is good in the state of Vermont and Wyoming.
2.Sale of products such as Machines and Copiers are high and the least sold products are Labels,Fasterners,Art,Paper.
3.The category Technology yeilds the Maximum profit among Furniture and Office Supplies.
4.The sale is quite high in South region compared to West,Central and East region.
5.A high percent of discount is being offered on Furniture products.
6.The sale is not that welcomed in the state of Kansas.
7.The Shipping Mode of products have mostly been of Standard Class.
8.The Sale of Phone is almost high comapared to other office supplies among consumers.
```
## RESULT:
 Data Visualization is performed on the given complex dataset and insights about the data have been updated successfully. 
