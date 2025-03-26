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
![Screenshot 2025-03-26 154546](https://github.com/user-attachments/assets/fd7f0172-e641-417d-8ac2-bdbd6a482355)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```


```
sns.countplot(data=df,x="Survived", palette={"0": "blue", "1": "orange"})
```
![Screenshot 2025-03-26 154611](https://github.com/user-attachments/assets/8fd7e0ce-9915-44d6-9bac-77926a886c2d)



# RESULT
        <<INCLUDE YOUR RESULT HERE>>
