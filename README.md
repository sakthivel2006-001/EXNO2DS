# EXNO2DS
## SAKTHIVEL S
## 212223220090
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
df=pd.read_csv("titanic_dataset.csv")
df
```
<img width="1447" height="493" alt="image" src="https://github.com/user-attachments/assets/a82fc566-19fb-4989-aba0-63df268b9b50" />

```
df.info()
```
<img width="453" height="432" alt="image" src="https://github.com/user-attachments/assets/712d492a-beb1-4c7c-a340-df295b7416ce" />

```
df.dtypes
```
<img width="245" height="552" alt="image" src="https://github.com/user-attachments/assets/8dc252a4-dcc7-4e85-9e11-4ff1cf548eff" />

```
df.describe()
```
<img width="878" height="355" alt="image" src="https://github.com/user-attachments/assets/0457defa-b8ff-4e97-b948-60e44377440c" />

```
df.values_counts()
```
<img width="1597" height="588" alt="image" src="https://github.com/user-attachments/assets/22021f0a-9ac0-4006-b3b8-0e16b5cb0691" />

```
df['Age'].value_counts()
```
<img width="171" height="598" alt="image" src="https://github.com/user-attachments/assets/5fb74959-6d83-436d-8a46-96a0b42c497b" />

```
df.shape
```
<img width="98" height="21" alt="image" src="https://github.com/user-attachments/assets/bb3081e6-5df2-449e-adcc-c7a67930ed03" />

```
df.set_index('PassengerId',inplace=True)
df.describe()
```
<img width="732" height="358" alt="image" src="https://github.com/user-attachments/assets/7a4d7860-fc8c-4dad-aca3-82bbb09b862c" />

```
df.nunique()
```
<img width="157" height="530" alt="image" src="https://github.com/user-attachments/assets/08d3fb3a-0435-4e99-a6f8-eb193ed3710d" />

```
sns.countplot(x='Survived',data=df)
```
<img width="771" height="580" alt="image" src="https://github.com/user-attachments/assets/5f07bbe2-7781-423d-be19-34848f3b92bc" />

```
df.Pclass.unique()
```
<img width="157" height="32" alt="image" src="https://github.com/user-attachments/assets/8403013e-35e1-4816-a68f-706cf144bebd" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1416" height="551" alt="image" src="https://github.com/user-attachments/assets/88740e32-ad7e-4ebd-80b9-30608afa5c6b" />

```
sns.catplot(x='Gender',col='Survived',data=df,kind='count',height=5,aspect=.7)
```
<img width="891" height="657" alt="image" src="https://github.com/user-attachments/assets/d0fe7fb6-4d41-4be5-b074-49603fa45d2c" />

```
df.boxplot(by='Survived',column=['Age'])
```
<img width="772" height="605" alt="image" src="https://github.com/user-attachments/assets/3ed2e15f-9a08-4c9e-8d80-956c2409fe97" />

```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
<img width="768" height="581" alt="image" src="https://github.com/user-attachments/assets/958c5da4-381d-4858-8dc8-ce498eb568bd" />

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="882" height="580" alt="image" src="https://github.com/user-attachments/assets/ce48c170-bf54-4fbb-be7b-a1dc9adca281" />

```
plt = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="732" height="548" alt="image" src="https://github.com/user-attachments/assets/38c2e2ea-0131-49a7-ab32-95c4f15aeee3" />

```
sns.catplot(data=df,col='Survived',x='Gender',hue='Pclass',kind='count')
```
<img width="1358" height="656" alt="image" src="https://github.com/user-attachments/assets/e02696c6-d3b8-4881-8234-d10e66874fca" />

```
numeric_df = df.select_dtypes(include=np.number)
corr=numeric_df.corr()
sns.heatmap(corr,annot=True)
```
<img width="692" height="566" alt="image" src="https://github.com/user-attachments/assets/2f85973f-7add-41db-998b-cdef53a03a4c" />

```
numeric_df = df.select_dtypes(include=np.number)
corr=numeric_df.corr()
sns.heatmap(corr)
```
<img width="697" height="542" alt="image" src="https://github.com/user-attachments/assets/b82ec4bc-8be2-4ae1-b66a-2dd018539779" />




















# RESULT
We Have performed Exploratory Data Analysis on the given data set successfully

