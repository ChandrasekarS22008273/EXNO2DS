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

## CODING AND OUTPUT:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df = pd.read_csv('/content/titanic_dataset.csv')
print(df.head())
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/ab9b236f-ad07-46d4-a147-01eaa7f7ce32)

```
df.info()
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/14425e41-26ce-4c3b-a999-c52355e28513)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/d1da1b10-0788-4c78-b724-2931d534ec9c)

```
df.nunique()
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/887b41bc-1727-4b5d-9a6d-5cd730650950)

```
df.shape
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/17a0b981-1eca-4b42-afd3-b7270483fa92)

```
df["Survived"].value_counts()
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/3b3b33b0-3d66-4b7d-99b1-e327f6cba659)

```
person=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
person
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/6430941a-ae1d-4e33-bb5f-828c398bb43e)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/38c0a54d-c706-40c9-8534-5300f85eb010)
```
df.Pclass.unique()
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/85407499-7ac3-46db-80a9-d755ffb47595)
```
df.rename(columns ={'Sex': 'Gender'}, inplace = True)
df
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/dd130af7-0021-4681-9f52-65f83af7dbed)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=0.7,color="Lightgreen")
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/4ee1b6b5-d41d-4769-8cc1-4c7cdb936dbd)
```
sns. catplot(x='Survived', hue="Gender",data=df, kind = "count" )
```
![image](https://github.com/ChandrasekarS22008273/EXNO2DS/assets/119643845/09fab659-4614-473d-940f-43f753c9bff7)
```
df.boxplot(column="Age", by="Survived")
```
![image](https://github.com/Saravana-kumar369/EXNO2DS/assets/117925254/00e9539e-8bb1-4b38-b8a9-b872e9dd4e6a)
```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
![image](https://github.com/Saravana-kumar369/EXNO2DS/assets/117925254/4838f5ad-576c-45fb-bf28-6968b3eeefc7)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/Saravana-kumar369/EXNO2DS/assets/117925254/95659236-ef27-4e13-8cfc-29634756560e)
```
fig, ax1= plt.subplots(figsize=(8,5))
pt=sns.boxplot (ax=ax1,x='Pclass',y='Age' ,hue= 'Gender', data=df)
```
![image](https://github.com/Saravana-kumar369/EXNO2DS/assets/117925254/dd3cfa1a-502d-4163-b7bd-a06ede59c686)
```
sns. catplot(data=df, col = "Survived",x = "Gender", hue="Pclass", kind = "count" )
```
![image](https://github.com/Saravana-kumar369/EXNO2DS/assets/117925254/a29e41b4-50df-44cb-b346-53aad5f612d1)
```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/Saravana-kumar369/EXNO2DS/assets/117925254/1f4ebbae-2cce-4842-a634-314ed03eccf3)
```
sns.pairplot(df)
```
![image](https://github.com/Saravana-kumar369/EXNO2DS/assets/117925254/9ddcfac2-4cdf-4ff4-8666-462fe3dbd3c7)
# RESULT:
  Thus  Exploratory Data Analysis on the given data set executed successfully.
