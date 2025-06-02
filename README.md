# EXNO2DS-Exploratory Data Analysis
## AIM:
  To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
 The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
### Developed by: Vishal S
### Register no: 212222040181
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/db11f80c-4a17-4e94-b6e8-aee84c2f4589)

```py
df.info()
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/0afba499-0472-4086-a983-7bbcbcf882ac)

```py
df.shape
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/3ef6f1fb-6669-4841-80b0-0bdbc119037f)

```py
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/422739d7-3b68-40ee-a6de-bce2125e9f79)

```py
df.shape
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/971f1540-0365-4153-aa09-48207a6c3b50)

### Categorical data analysis
```py
df.nunique()
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/2f914a14-d6dd-46bd-a5d2-8dd41b9eabba)

```py
df["Survived"].value_counts()
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/b7bf64d4-d87c-44c2-a5c4-dd30e6d779be)

```py
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/4489bb91-1ebb-4209-ba7b-8fecb0488b92)

```py
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/79e00eb4-aff2-4eff-9fdd-0b4795dd9a91)

```py
df
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/248bd14a-bd96-4f1c-9900-88b12f52cf41)

```py
df.Pclass.unique()
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/c3732921-a9aa-4129-85a0-7a8b17ff2f46)

```py
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/b1e5548b-1f7d-42fe-b874-c54a51755953)

### Bivariate Analysis
```py
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/bda06792-7241-43b4-bdbd-0373a40156da)

```py
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/0fadff81-af90-4e3b-9b15-84532b4a828a)

```py
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/ab644f3b-2091-4b0f-82d6-1448192c7d39)

```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/58779838-955e-46ac-82b5-a70ddfbbacdf)

```py
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/7c1b6cb5-4f85-4d21-ad54-ec56220992c4)

### Multivariate Analysis
```py
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/8fe0c379-9549-42ca-b1cc-0cf6c3096acc)

```py
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/a41c58a9-0cb4-4f1b-865b-9cdaf0eb1c05)

# Co-relation
```py
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/73540fe3-fb91-42bd-940d-42e9788b0893)

```py
sns.pairplot(df)
```
![image](https://github.com/PSriVarshan/EXNO2DS/assets/114944059/73695887-75ec-4035-8065-4b178f7d6849)

## RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
