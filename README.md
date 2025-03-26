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

df = pd.read_csv(r"C:\Users\Suriya\Downloads\titanic_dataset.csv")
df
```
![Screenshot 2025-03-26 154452](https://github.com/user-attachments/assets/1716a007-18d5-412f-bfb4-5a790b0a3593)



```
df.info()
```
![Screenshot 2025-03-26 154505](https://github.com/user-attachments/assets/d9c687ca-35cb-49e1-8fa8-d41e4f538714)



```
df.shape
```
![Screenshot 2025-03-26 154523](https://github.com/user-attachments/assets/43d3915f-7412-49b8-b423-d829a9b42f08)




```
df.set_index("PassengerId", inplace=True)
df.describe()
```

![Screenshot 2025-03-26 154533](https://github.com/user-attachments/assets/652684dd-bc05-43ce-bbd0-2689360e259d)


```
df.shape
```

![Screenshot 2025-03-26 154540](https://github.com/user-attachments/assets/27621094-dd91-4ec3-9ca6-f690aead9813)



```
df.nunique()
```
![Screenshot 2025-03-26 154546](https://github.com/user-attachments/assets/b559bbcf-7589-4a7b-b5f1-300e43812783)


```
df["Survived"].value_counts()
```
![Screenshot 2025-03-26 160110](https://github.com/user-attachments/assets/b04d4e3b-5622-4a22-be25-65b890285e0c)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2025-03-26 160118](https://github.com/user-attachments/assets/fcf30ad5-934c-490e-9cfe-94ca92430991)


```
sns.countplot(data=df,x="Survived", palette={"0": "blue", "1": "orange"})
```
![Screenshot 2025-03-26 154611](https://github.com/user-attachments/assets/8fd7e0ce-9915-44d6-9bac-77926a886c2d)

```
df
```
![Screenshot 2025-03-26 160647](https://github.com/user-attachments/assets/a8365d86-ded9-490d-b53d-27b7a125d09c)





```
df.Pclass.unique()
```
![Screenshot 2025-03-26 160659](https://github.com/user-attachments/assets/3a07372e-b873-476d-af8c-5cc7a174a7d7)



```
df.rename(columns={'Sex':'Gender'},inplace=True)
df

```


![Screenshot 2025-03-26 160712](https://github.com/user-attachments/assets/5c998169-9568-46b1-b746-022be9497a5d)



```
sns.catplot(x="Gender", col="Survived", kind="count", data=df, height=5, aspect=0.7, palette={"male": "blue", "female": "orange"})
```

![Screenshot 2025-03-26 160722](https://github.com/user-attachments/assets/341a90e8-a3f3-4d85-96ff-b38ce7e2c2c1)


```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```

![Screenshot 2025-03-26 160729](https://github.com/user-attachments/assets/daca108a-f458-4369-9ed2-7659457f404c)


```
df.boxplot(column="Age",by="Survived")
```

![Screenshot 2025-03-26 160736](https://github.com/user-attachments/assets/00864768-1c75-4a3a-a0f4-0b2ed0434177)




```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

![Screenshot 2025-03-26 160743](https://github.com/user-attachments/assets/761c8ac2-0ca5-40fe-a82d-970f5da9a0d2)


```
sns.jointplot(x="Age",y="Fare",data=df)
```

![Screenshot 2025-03-26 160749](https://github.com/user-attachments/assets/81dab586-1e5e-4c00-938c-222a00a2ea0a)




```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

![Screenshot 2025-03-26 160758](https://github.com/user-attachments/assets/af0a32a5-206a-474f-a706-1822621a8740)



```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![Screenshot 2025-03-26 160809](https://github.com/user-attachments/assets/41f5583f-1971-4bce-952a-5010815b8c3f)


```
corr = df.select_dtypes(include=['number']).corr()
sns.heatmap(corr, annot=True)
```


![Screenshot 2025-03-26 160817](https://github.com/user-attachments/assets/28bcdbaf-3fe1-4fc3-ab9c-cc65137fac7b)


```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/12f2b145-7d66-43ed-81e8-fc97f7a18c0a)






# RESULT
        <<INCLUDE YOUR RESULT HERE>>
