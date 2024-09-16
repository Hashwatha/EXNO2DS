# EXNO2DS
# AIM:
To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
df = pd.read_csv('/content/titanic_dataset.csv')
df
```
![image](https://github.com/user-attachments/assets/15d9ac2b-a31a-40f3-a8e8-cf0046902dbc)
```
df.info()
```
![image](https://github.com/user-attachments/assets/bad73393-a351-4919-be65-6ef2cca1980f)
```
df.shape
```
![image](https://github.com/user-attachments/assets/636b3b1d-b2c8-44b0-9caa-dcd5fd0bbf25)
```
df.describe()
```
![image](https://github.com/user-attachments/assets/bd17fb07-d4f3-466b-98ec-0ada5fdb9683)
```
df
```
![image](https://github.com/user-attachments/assets/40a61f57-9502-449e-9236-db9e4b9c7d22)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/29366f08-0713-4f94-94df-e1946e5add04)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/1526fc05-a29e-42af-8330-ea0fa01185ac)
```
per=(df['Survived'].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/60c5bdf0-00a8-4474-b689-d8c084e1a2b9)
```
sns.countplot(x='Survived',data=df)
```
![image](https://github.com/user-attachments/assets/a9f5f00a-c5ed-4df1-91db-d708bbccfe7d)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/2a7e19ad-1aee-4e8d-8baa-30f302cf183a)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/72ef5986-8080-4721-b6de-ea5ac319486b)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/ac1c487d-6c67-408d-89fa-03de24033d08)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/b4f8e51d-55df-48a2-a66d-10250556a737)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/3b6749fe-78c7-4440-a475-c5ccde7d3045)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/f8acd1d3-0dd8-483d-a835-4dee626f90fe)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/dceef334-8c47-4709-a963-7b06c9c44ae5)
```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y="Age",hue="Gender",data=df)
```
![image](https://github.com/user-attachments/assets/1ef223df-9641-45e7-bc08-0b965d5944a2)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/5b95c836-3cef-4a00-a8fd-36f97207397a)
```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/d3e522b0-4c0e-4c80-b7de-ff95300b50f1)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/d377b8a4-06e3-4cf6-b5aa-28e953159671)

# RESULT
Thus the given program executed successfully.
