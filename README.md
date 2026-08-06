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
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
<img width="1917" height="1026" alt="image" src="https://github.com/user-attachments/assets/e16ba1be-54a6-4b6d-91d6-e695df062955" />

```
dt.info()
```

<img width="1917" height="900" alt="image" src="https://github.com/user-attachments/assets/65b624a7-953d-4571-a876-12ebe082b5a9" />

```
dt.shape
```
<img width="1917" height="398" alt="image" src="https://github.com/user-attachments/assets/9bcf0860-b4f4-423d-83fa-baf988e225ce" />

```
dt.nunique()
```
<img width="1917" height="1022" alt="image" src="https://github.com/user-attachments/assets/5482f1ee-6d1e-452c-be4a-8c06b8fadcf1" />

```
dt["Survived"].value_counts()
```
<img width="1827" height="293" alt="image" src="https://github.com/user-attachments/assets/79584969-ed4d-412f-9fe7-d078822bf4b1" />

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

<img width="1823" height="312" alt="image" src="https://github.com/user-attachments/assets/c09ea747-299b-4bc8-b0bc-ee8a7eadbaf6" />

```
sns.countplot(data=dt,x="Survived")
```

<img width="1915" height="971" alt="image" src="https://github.com/user-attachments/assets/db85ab3a-c971-4fdf-ad0a-f713cfb6bd17" />

```
dt
```

<img width="1917" height="912" alt="image" src="https://github.com/user-attachments/assets/3df023a3-0dcb-4049-ad9f-0174236bf98e" />

```
dt.Pclass.unique()
```
<img width="1912" height="467" alt="image" src="https://github.com/user-attachments/assets/f05d5422-7056-48c3-bec6-729195955d9e" />

```
dt.rename(columns = {'sex':'Gender'},inplace=True)
dt
```
<img width="1917" height="931" alt="image" src="https://github.com/user-attachments/assets/fb38b644-2971-4c48-9ed5-043beab0a81b" />

```
sns.catplot(x="Sex",col="Survived",kind="count",data=dt,height=5, aspect=.7)
```

<img width="1917" height="1003" alt="image" src="https://github.com/user-attachments/assets/d30c30d2-894b-4337-9d18-4f5e2dd9688a" />

```
import seaborn as sns

sns.catplot(x='Survived', hue='Sex', data=dt, kind='count')
```

<img width="1917" height="993" alt="image" src="https://github.com/user-attachments/assets/b80efadd-4629-4daa-b15f-52d9d29c1931" />

```
dt.boxplot(column="Age",by="Survived")
```

<img width="1917" height="1000" alt="image" src="https://github.com/user-attachments/assets/9caafedd-0eaa-49da-9efe-c51c3afb1d39" />

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

<img width="1917" height="927" alt="image" src="https://github.com/user-attachments/assets/ef6b4b9d-0592-40a2-8e26-5b9651768b84" />

```
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=dt)
```

<img width="1917" height="957" alt="image" src="https://github.com/user-attachments/assets/148bc005-86f0-4dd0-b797-0ae91916de33" />

```
sns.catplot(data=dt,col="Survived",x="Sex",hue="Pclass",kind="count")
```

<img width="1917" height="1007" alt="image" src="https://github.com/user-attachments/assets/4229fb2d-9ad3-4c2a-beff-d96033d8624f" />

```
corr = dt.select_dtypes(include='number').corr()
sns.heatmap(corr, annot=True)
plt.show()
```

<img width="1913" height="1032" alt="image" src="https://github.com/user-attachments/assets/a680d12e-5c32-4072-829f-de4c7b1c5ed9" />

```
sns.pairplot(dt)
```

<img width="1917" height="1023" alt="image" src="https://github.com/user-attachments/assets/49adc40c-fb22-469b-acf6-ad2449652207" />
<img width="1906" height="946" alt="image" src="https://github.com/user-attachments/assets/8163d679-3495-4c3c-a79d-66b4d7b6158d" />
<img width="1781" height="357" alt="image" src="https://github.com/user-attachments/assets/d768e8a5-0a34-448c-8269-a79fb9c4abb0" />



# RESULT
        <<INCLUDE YOUR RESULT HERE>>
