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
df=pd.read_csv("C:\\Users\\Pandiyan\\Downloads\\titanic_dataset.csv")
df
```
<img width="894" height="745" alt="image" src="https://github.com/user-attachments/assets/de6f2c9b-1f6e-4c98-977e-a2f050f18739" />

```
df.shape
```
<img width="198" height="63" alt="image" src="https://github.com/user-attachments/assets/5f9abfa5-15f7-4e9b-a6df-a2b9d0fb9738" />

```
df.nunique()
```

<img width="261" height="292" alt="image" src="https://github.com/user-attachments/assets/5566a697-7f40-4746-bd16-fc8a3241658b" />

```
df['Sex'].value_counts()
```
<img width="348" height="134" alt="image" src="https://github.com/user-attachments/assets/51fbee21-f384-4c0d-afed-ff69d135e15b" />
```
df.Survived.unique()
```
<img width="183" height="53" alt="image" src="https://github.com/user-attachments/assets/50fda520-3a86-4776-9324-ebe8fd641d44" />
```
df.rename(columns={"Sex":"Gender"},inplace=True)
df
```
<img width="1453" height="538" alt="image" src="https://github.com/user-attachments/assets/079f5a30-d117-4dbe-9081-8a718de3317d" />
```
import seaborn as sns
sns.countplot(data=df)
```

<img width="931" height="566" alt="image" src="https://github.com/user-attachments/assets/11a3f155-8600-4f78-a43b-afcc600319c5" />

```
sns.countplot(x="Survived",hue="Gender",data=df)
```

<img width="907" height="573" alt="image" src="https://github.com/user-attachments/assets/fd7171dd-d931-4cbb-ae61-6d2f04cbde8a" />

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
<img width="843" height="636" alt="image" src="https://github.com/user-attachments/assets/37f53443-e2ae-4851-9c32-4a3cebbc9aab" />

```
sns.boxplot(data=df)
```

<img width="830" height="548" alt="image" src="https://github.com/user-attachments/assets/c0719a6c-4032-47cc-8d0a-161ff47dc81e" />

```
df.boxplot(column="Survived",by="Gender")
```

<img width="820" height="640" alt="image" src="https://github.com/user-attachments/assets/20993888-77c0-48eb-9a2c-76ba299756cc" />

```
sns.scatterplot(data=df)
```
<img width="847" height="579" alt="image" src="https://github.com/user-attachments/assets/017fad40-11c1-43cc-bdbb-fc4879704a96" />

```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
<img width="840" height="577" alt="image" src="https://github.com/user-attachments/assets/1ec142f6-839f-41a7-a8b0-743cd34551ac" />

```
sns.jointplot(x='Age',y='Fare',data=df,kind="hist")
```

<img width="841" height="725" alt="image" src="https://github.com/user-attachments/assets/8d0823c1-ca2f-4be6-a079-f19eb6154847" />

```
sns.pairplot(data=df)
```
<img width="1640" height="670" alt="image" src="https://github.com/user-attachments/assets/8f58c5e4-543d-432b-a615-22e3cbf8c179" />

<img width="1526" height="746" alt="image" src="https://github.com/user-attachments/assets/56a89993-74bf-49de-b323-b4431e33d0d8" />

```
corr1 = df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1, annot=True)
```

<img width="637" height="571" alt="image" src="https://github.com/user-attachments/assets/bb8263aa-c6ec-4db6-b943-77c4c9aa1761" />

# RESULT
Thus we have clened the data and removed the outliers by detection using IQR and Z-score method.
